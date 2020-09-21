---
title: Saját osztályozó kialakítása a QDK
description: Megtudhatja, hogyan tervezhet áramköri modelleket a Quantum Circuit központú osztályozó számára.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: c87a84654cda04f81115a83684f0e125d23a77bc
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759221"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="40969-103">Saját osztályozó tervezése</span><span class="sxs-lookup"><span data-stu-id="40969-103">Design your own classifier</span></span>

<span data-ttu-id="40969-104">Ebben az útmutatóban megismerheti a Quantum Circuit központú osztályozó áramköri modelljeinek kialakításához szükséges alapvető fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="40969-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="40969-105">A klasszikus mély tanuláshoz hasonlóan nincs általános szabály egy adott architektúra kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="40969-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="40969-106">A probléma függvényében egyes architektúrák jobban teljesítenek, mint mások.</span><span class="sxs-lookup"><span data-stu-id="40969-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="40969-107">Vannak azonban olyan fogalmak is, amelyek hasznosak lehetnek az áramkör tervezésekor:</span><span class="sxs-lookup"><span data-stu-id="40969-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="40969-108">A nagy számú paraméter egy rugalmasabb modellt tesz szükségessé, amely alkalmas lehet a bonyolult besorolási határok rajzolására, de az is elképzelhető, hogy a túlilleszkedés is érzékenyebb.</span><span class="sxs-lookup"><span data-stu-id="40969-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="40969-109">A qubits közötti összekapcsolási kapuk elengedhetetlenek a kvantum-funkciók közötti korrelációk rögzítéséhez.</span><span class="sxs-lookup"><span data-stu-id="40969-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="40969-110">Osztályozó létrehozása a Q használatával\#</span><span class="sxs-lookup"><span data-stu-id="40969-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="40969-111">Az osztályozó kiépítéséhez a parametrized-vezérelt rotációkat fogjuk összefűzni az áramköri modellben.</span><span class="sxs-lookup"><span data-stu-id="40969-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="40969-112">Ehhez a [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) Quantum Machine learning könyvtárban definiált típust használhatjuk.</span><span class="sxs-lookup"><span data-stu-id="40969-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="40969-113">Ez a típus négy argumentumot fogad el: a cél qubit indexét, a vezérlőelem qubits indexét, a forgatás tengelyét, valamint a társított paraméter indexét a modellt meghatározó paraméterek tömbben.</span><span class="sxs-lookup"><span data-stu-id="40969-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="40969-114">Lássunk egy példát a besorolásra.</span><span class="sxs-lookup"><span data-stu-id="40969-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="40969-115">A [Half-Moons mintában](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)a következő, a fájlban definiált osztályozó található `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="40969-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="40969-116">Az itt definiált függvények az elemek tömbjét visszaadó függvény `ControlledRotation` , amely a paraméterek tömbjét és a torzítást is meghatározza [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) .</span><span class="sxs-lookup"><span data-stu-id="40969-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="40969-117">Ez a típus alapvető fontosságú a Quantum Machine Learning könyvtárban, és meghatározza az osztályozó értéket.</span><span class="sxs-lookup"><span data-stu-id="40969-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="40969-118">A fenti függvényben meghatározott kör egy olyan osztályozó része, amelyben az adatkészlet mindegyik mintája két funkciót tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="40969-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="40969-119">Ezért csak két qubits van szükség.</span><span class="sxs-lookup"><span data-stu-id="40969-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="40969-120">Az áramkör grafikus ábrázolása:</span><span class="sxs-lookup"><span data-stu-id="40969-120">The graphical representation of the circuit is:</span></span>

 ![Példa áramköri modellre](~/media/circuit_model_1.PNG)

<span data-ttu-id="40969-122">Vegye figyelembe, hogy alapértelmezés szerint a Quantum Machine Learning Library műveletei a regisztráció utolsó qubit mérik a besorolási valószínűségek becslése érdekében.</span><span class="sxs-lookup"><span data-stu-id="40969-122">Note that by default the operations of the Quantum Machine Learning library measure the last qubit of the register to estimate the classification probabilities.</span></span> <span data-ttu-id="40969-123">Ezt a tényt érdemes figyelembe vennie az áramkör tervezésekor.</span><span class="sxs-lookup"><span data-stu-id="40969-123">You should keep in mind this fact when designing your circuit.</span></span>

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="40969-124">A könyvtár függvények használata a Gates rétegeinek írásához</span><span class="sxs-lookup"><span data-stu-id="40969-124">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="40969-125">Tegyük fel, hogy egy 784-es funkciókkal rendelkező adatkészletet használunk, például: 28 × 28 képpont, például a MNIST adathalmaz.</span><span class="sxs-lookup"><span data-stu-id="40969-125">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="40969-126">Ebben az esetben az áramkör szélessége elég nagy lesz, így az egyes kapuk általi írás is lehetséges, de nem praktikus feladat lesz.</span><span class="sxs-lookup"><span data-stu-id="40969-126">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="40969-127">Ezért a Quantum Machine Learning Library olyan eszközöket biztosít, amelyekkel automatikusan hozhat létre parametrized-rotációs rétegeket.</span><span class="sxs-lookup"><span data-stu-id="40969-127">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="40969-128">A függvény például [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) visszaadja a nem vezérelt qubit-rotációk tömbjét egy adott tengelyen, egy rotációs értékkel a regiszter minden egyes qubit, az egyes parametrized egy másik modell-paraméterrel.</span><span class="sxs-lookup"><span data-stu-id="40969-128">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="40969-129">Például `LocalRotationsLayer(4, X)` a következő Gates-készletet adja vissza:</span><span class="sxs-lookup"><span data-stu-id="40969-129">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Helyi elforgatások réteg](~/media/local_rotations_layer.PNG)

<span data-ttu-id="40969-131">Javasoljuk, hogy ismerkedjen meg a [Quantum Machine learning Library API-referenciával](xref:microsoft.quantum.machinelearning) , és fedezze fel az áramköri terv egyszerűsítéséhez rendelkezésre álló összes eszközt.</span><span class="sxs-lookup"><span data-stu-id="40969-131">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="40969-132">További lépések</span><span class="sxs-lookup"><span data-stu-id="40969-132">Next steps</span></span>

 <span data-ttu-id="40969-133">Próbálkozzon különböző struktúrákkal a minták által megadott példákban.</span><span class="sxs-lookup"><span data-stu-id="40969-133">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="40969-134">Megjelenik a modell teljesítményében bekövetkezett változás?</span><span class="sxs-lookup"><span data-stu-id="40969-134">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="40969-135">A következő oktatóanyagban [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) megtudhatja, hogyan tölthet be adatkészleteket az osztályozók új architektúráinak kipróbálásához és megismeréséhez.</span><span class="sxs-lookup"><span data-stu-id="40969-135">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
