---
title: Kvantum-véletlenszámgenerátor létrehozása
description: Elkészíthet egy Q#-projektet, amely bemutatja az alapvető kvantumfogalmakat, például a kvantum-véletlenszámgenerátor létrehozása általi szuperpozíciót.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443919"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="c930a-103">Gyorsútmutató: Kvantum-véletlenszámgenerátor implementálása a Q#-ban</span><span class="sxs-lookup"><span data-stu-id="c930a-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="c930a-104">A Q#-ban írt kvantumalgoritmusok egyik egyszerű példája egy kvantum-véletlenszámgenerátor.</span><span class="sxs-lookup"><span data-stu-id="c930a-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="c930a-105">Ez az algoritmus a kvantummechanika természetét használja ki egy véletlen szám előállításához.</span><span class="sxs-lookup"><span data-stu-id="c930a-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c930a-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c930a-106">Prerequisites</span></span>

- <span data-ttu-id="c930a-107">A Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="c930a-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="c930a-108">Q#-projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="c930a-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="c930a-109">Q#-művelet írása</span><span class="sxs-lookup"><span data-stu-id="c930a-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="c930a-110">Q#-műveletkód</span><span class="sxs-lookup"><span data-stu-id="c930a-110">Q# operation code</span></span>

1. <span data-ttu-id="c930a-111">Cserélje le az Operation.qs fájl tartalmát a következő kódra:</span><span class="sxs-lookup"><span data-stu-id="c930a-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="c930a-112">Ahogy a [Mi az a kvantum-számítástechnika?](xref:microsoft.quantum.overview.what) című cikkben említettük, a qubit a kvantuminformáció egysége, amely szuperpozícióban lehet.</span><span class="sxs-lookup"><span data-stu-id="c930a-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="c930a-113">Ha megmérjük, a qubit értéke csak 0 vagy 1 lehet.</span><span class="sxs-lookup"><span data-stu-id="c930a-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="c930a-114">Végrehajtás során azonban a qubit állapota a 0 vagy 1 érték méréssel történő leolvasásának valószínűségét jelzi.</span><span class="sxs-lookup"><span data-stu-id="c930a-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="c930a-115">Ezt a valószínűségi állapotot nevezzük szuperpozíciónak.</span><span class="sxs-lookup"><span data-stu-id="c930a-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="c930a-116">E valószínűség segítségével generálhatunk véletlen számokat.</span><span class="sxs-lookup"><span data-stu-id="c930a-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="c930a-117">A Q#-műveletben bevezetjük a Q#-ban natív `Qubit` adattípust.</span><span class="sxs-lookup"><span data-stu-id="c930a-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="c930a-118">Egy `Qubit` csak a `using` utasítással foglalható le.</span><span class="sxs-lookup"><span data-stu-id="c930a-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="c930a-119">Lefoglalás esetén a qubit mindig `Zero` állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="c930a-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="c930a-120">A `H` művelet használatával a `Qubit` szuperpozícióba helyezhető.</span><span class="sxs-lookup"><span data-stu-id="c930a-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="c930a-121">A qubit megméréséhez és értékének leolvasásához használja az `M` belső műveletet.</span><span class="sxs-lookup"><span data-stu-id="c930a-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="c930a-122">A `Qubit` szuperpozícióba történő helyezésekor és megmérésekor az eredmény más érték lesz a kód meghívásának minden alkalmával.</span><span class="sxs-lookup"><span data-stu-id="c930a-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="c930a-123">A `Qubit` lefoglalásának feloldásakor kifejezetten vissza kell állítani a `Zero` állapotba, máskülönben a szimulátor futásidejű hibát fog jelenteni.</span><span class="sxs-lookup"><span data-stu-id="c930a-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="c930a-124">Ennek elérésére az egyik legegyszerűbb módszer a `Reset` meghívása.</span><span class="sxs-lookup"><span data-stu-id="c930a-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="c930a-125">A kód vizualizálása a Bloch-gömbbel</span><span class="sxs-lookup"><span data-stu-id="c930a-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="c930a-126">A Bloch-gömbön az északi pólus a **0** klasszikus értéket jelöli, a déli pólus pedig az **1** klasszikus értéket.</span><span class="sxs-lookup"><span data-stu-id="c930a-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="c930a-127">Minden szuperpozíció megadható a gömb egyik pontjaként (ezt a nyíl jelzi).</span><span class="sxs-lookup"><span data-stu-id="c930a-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="c930a-128">Minél közelebb van a nyíl hegye a pólushoz, annál nagyobb a valószínűsége, hogy a qubit a mérésekor a pólushoz hozzárendelt klasszikus értékkel esik egybe.</span><span class="sxs-lookup"><span data-stu-id="c930a-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="c930a-129">Az alábbi ábrán például a piros nyíllal jelölt qubitállapot esetében nagyobb a valószínűsége a **0** értéknek, ha megmérjük.</span><span class="sxs-lookup"><span data-stu-id="c930a-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="c930a-130">Ennek az ábrának a segítségével vizualizálhatjuk a kód működését:</span><span class="sxs-lookup"><span data-stu-id="c930a-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="c930a-131">Először is egy **0** állapotban inicializált qubittel kezdünk, és a `H` alkalmazásával létrehozunk egy szuperpozíciót, amelyben a **0** és az **1** valószínűsége egyenlő.</span><span class="sxs-lookup"><span data-stu-id="c930a-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="c930a-132">Ezután megmérjük a qubitet, és mentjük a kimenetet:</span><span class="sxs-lookup"><span data-stu-id="c930a-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="c930a-133">A mérés eredménye teljesen véletlen, tehát egy véletlen bitből kaptuk meg.</span><span class="sxs-lookup"><span data-stu-id="c930a-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="c930a-134">Ezt a függvényt többször is meghívhatjuk egész számok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c930a-134">We can call this function several times to create integers.</span></span> <span data-ttu-id="c930a-135">Ha például háromszor hívjuk meg a függvényt, hogy három véletlen bitet kapjunk, véletlen hárombites számokat hozhatunk létre (tehát egy 0 és 7 közötti véletlen számot).</span><span class="sxs-lookup"><span data-stu-id="c930a-135">For example, if we call the function three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>
