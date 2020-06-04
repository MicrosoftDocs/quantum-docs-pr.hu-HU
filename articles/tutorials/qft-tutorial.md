---
title: 'Qubit-szintű programok írása és szimulálása a Q-ban #'
description: Lépésenkénti oktatóanyag egy olyan kvantum-program írásához és szimulálásához, amely az egyes qubit szintjén működik
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: f0b87936c9baf07555e76f295da58c0a6b9ecd17
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84328595"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="ff9ca-103">Oktatóanyag: qubit-szintű programok írása és szimulálása a Q-ban\#</span><span class="sxs-lookup"><span data-stu-id="ff9ca-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="ff9ca-104">Üdvözöljük a Quantum Development Kit oktatóanyagban, amely egy alapszintű, egyedi qubits működő kvantum-program írását és szimulálása.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="ff9ca-105">Bár a Q # elsődlegesen a nagyméretű kvantum-programok magas szintű programozási nyelve volt, a legkönnyebben használható a kvantum-programok alacsonyabb szintjének feltárására: adott qubits közvetlen kezelése.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="ff9ca-106">A Q # rugalmassága lehetővé teszi a felhasználók számára, hogy bármely ilyen szintű absztrakcióból megközelítsék a kvantum-rendszereket, és ebben az oktatóanyagban a qubits magukat.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="ff9ca-107">Pontosabban tekintse meg a [Quantum Fourier-transzformáció](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)csuklyáját, amely egy olyan alrutin, amely a sok nagyobb kvantum-algoritmus szerves részét képezi.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="ff9ca-108">Vegye figyelembe, hogy a kvantum-adatok feldolgozásának alacsony szintű nézetét gyakran a "[Quantum áramkörök](xref:microsoft.quantum.concepts.circuits)" kifejezés írja le, amely a kapuk szekvenciális alkalmazását jelöli a rendszer adott qubits.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="ff9ca-109">Így az egy-és többqubitos műveletek, amelyeket szekvenciálisan alkalmazunk, könnyen szerepelhetnek egy "áramköri diagramban".</span><span class="sxs-lookup"><span data-stu-id="ff9ca-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="ff9ca-110">A mi esetünkben a Q # műveletet fogjuk meghatározni a teljes három qubit Quantum Fourier-transzformáció végrehajtásához, amely a következő, áramkörként ábrázolt állapottal rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="ff9ca-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="ff9ca-111">Prerequisites</span></span>

* <span data-ttu-id="ff9ca-112">[Telepítse](xref:microsoft.quantum.install) a Quantum Development Kit-t az előnyben részesített nyelvi és fejlesztési környezet használatával.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="ff9ca-113">Ha a QDK már telepítve van, győződjön meg arról, hogy a legújabb verzióra van [frissítve](xref:microsoft.quantum.update).</span><span class="sxs-lookup"><span data-stu-id="ff9ca-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="ff9ca-114">Az oktatóanyag segítségével megtanulhatja a következőket:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="ff9ca-115">Kvantum-műveletek definiálása a Q-ban #</span><span class="sxs-lookup"><span data-stu-id="ff9ca-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="ff9ca-116">A Q # műveletek hívása közvetlenül a parancssorból vagy egy klasszikus gazda program használatával</span><span class="sxs-lookup"><span data-stu-id="ff9ca-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="ff9ca-117">Quantum művelet szimulálása qubit-kiosztásból a mérési kimenetre</span><span class="sxs-lookup"><span data-stu-id="ff9ca-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="ff9ca-118">Figyelje meg, hogyan fejlődik a Quantum System szimulált wavefunction a művelet során</span><span class="sxs-lookup"><span data-stu-id="ff9ca-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="ff9ca-119">A Quantum program a Microsoft Quantum Development Kit-vel való futtatása általában két részből áll:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="ff9ca-120">Maga a program, amely a Q # Quantum programozási nyelv használatával lett megvalósítva, majd egy kvantum-számítógépen vagy kvantum-szimulátoron való futtatásra hív meg.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="ff9ca-121">Ezek a következőkből állnak</span><span class="sxs-lookup"><span data-stu-id="ff9ca-121">These consist of</span></span> 
    - <span data-ttu-id="ff9ca-122">Q # műveletek: a kvantum-regisztereken eljáró alrutinok, és</span><span class="sxs-lookup"><span data-stu-id="ff9ca-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="ff9ca-123">Q # függvények: a kvantum-algoritmuson belül használt klasszikus alrutinok.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="ff9ca-124">A kvantum-program meghívásához használt belépési pont, és annak a célként megadott számítógépnek a megadása, amelyen futnia kell.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="ff9ca-125">Ezt közvetlenül a parancssorból vagy a klasszikus programozási nyelv, például a Python vagy a C# használatával írt gazda program segítségével végezheti el.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="ff9ca-126">Ez az oktatóanyag a tetszőleges módszerre vonatkozó utasításokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="ff9ca-127">Qubits foglalása és a kvantum-műveletek definiálása</span><span class="sxs-lookup"><span data-stu-id="ff9ca-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="ff9ca-128">Az oktatóanyag első része a Q # művelet definiálásával áll `Perform3qubitQFT` , amely a Quantum Fourier-transzformációt három qubits hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="ff9ca-129">Emellett a [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) függvény segítségével megfigyelheti, hogy a három qubit szimulált wavefunction hogyan fejlődik a művelet során.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="ff9ca-130">Első lépésként hozza létre a Q # projektet és a fájlt.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="ff9ca-131">Az ehhez szükséges lépések a program meghívásához használt környezettől függenek, és a részleteket a megfelelő [telepítési útmutatókban](xref:microsoft.quantum.install)találja.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="ff9ca-132">Lépésről lépésre végigvezeti a fájl összetevőin, de a kód az alábbi teljes blokkként is elérhető.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-q-operations"></a><span data-ttu-id="ff9ca-133">Névterek a többi Q # művelet eléréséhez</span><span class="sxs-lookup"><span data-stu-id="ff9ca-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="ff9ca-134">Először a fájlban definiáljuk a névteret, `NamespaceQFT` amelyet a fordító fog elérni.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="ff9ca-135">A meglévő Q # műveletek végrehajtásához a művelethez meg kell nyitnia a kapcsolódó `Microsoft.Quantum.<>` névtereket.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="ff9ca-136">Műveletek definiálása argumentumokkal és visszaadott értékekkel</span><span class="sxs-lookup"><span data-stu-id="ff9ca-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="ff9ca-137">Ezután definiáljuk a `Perform3qubitQFT` műveletet:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="ff9ca-138">Egyelőre a művelet nem vesz fel argumentumokat, és nem ad vissza semmit---ebben az esetben írunk, hogy egy olyan objektumot ad vissza `Unit` , amely a `void` C#-ban vagy egy üres rekordban van, `Tuple[()]` a Pythonban.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="ff9ca-139">Később módosítjuk, hogy a mérési eredmények tömbjét adja vissza, ekkor a rendszer a következőt váltja ki: `Unit` `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="ff9ca-140">Qubits foglalása a`using`</span><span class="sxs-lookup"><span data-stu-id="ff9ca-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="ff9ca-141">A Q # művelet keretében először három qubits-regisztrációt osztunk ki az `using` utasítással:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="ff9ca-142">A `using` esetében a qubits automatikusan le lesznek foglalva a $ \ket {0} $ állapotba.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="ff9ca-143">Ezt a és a használatával is [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) ellenőrizheti [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , amely kinyomtat egy karakterláncot és a rendszer aktuális állapotát a konzolra.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="ff9ca-144">A `Message(<string>)` és a `DumpMachine()` függvények (és/ [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) vagy [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) ) egyaránt közvetlenül a konzolra nyomtathatnak.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="ff9ca-145">A tényleges kvantum-számításokhoz hasonlóan a Q # nem teszi lehetővé az qubit-állapotok közvetlen elérését.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="ff9ca-146">`DumpMachine`A célszámítógép aktuális állapotának kinyomtatásakor azonban értékes információkat biztosíthat a hibakereséshez és a tanuláshoz, amikor a teljes állapotú szimulátorral együtt használja.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="ff9ca-147">Qubit és vezérelt kapuk alkalmazása</span><span class="sxs-lookup"><span data-stu-id="ff9ca-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="ff9ca-148">Ezután alkalmazzuk a kaput, amely magában foglalja a műveletet.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="ff9ca-149">A Q # már számos alapvető kvantum-kaput tartalmaz, mint a [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) névtérben végzett műveletek, és ezek nem kivételek.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="ff9ca-150">A Q # műveleten belül a callables meghívására szolgáló utasítások sorrendben lesznek végrehajtva.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="ff9ca-151">Ezért az elsőként alkalmazandó kapu a [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) az első qubit:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="ff9ca-152">Ha egy műveletet egy adott qubit szeretne alkalmazni egy regiszterből (azaz egy `Qubit` tömbből), a `Qubit[]` szabványos index jelölést használjuk.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="ff9ca-153">Tehát a [`H`](xref:microsoft.quantum.intrinsic.h) regisztráció első qubit a következő formában kell alkalmazni `qs` :</span><span class="sxs-lookup"><span data-stu-id="ff9ca-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="ff9ca-154">A `H` (Hadamard) kapunak az egyes qubits való alkalmazása mellett a QFT-áramkör elsősorban vezérelt [`R1`](xref:microsoft.quantum.intrinsic.r1) forgásokból áll.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="ff9ca-155">Egy `R1(θ, <qubit>)` általános művelet változatlanul hagyja a qubit $ \ket {0} $ összetevőjét, miközben a ($e ^ {i\theta} $ elforgatását alkalmazza a $ \ket {1} $ összetevőre.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="ff9ca-156">Vezérelt műveletek</span><span class="sxs-lookup"><span data-stu-id="ff9ca-156">Controlled operations</span></span>

<span data-ttu-id="ff9ca-157">A Q # lehetővé teszi a művelet végrehajtásának feltételét egy vagy több vezérlő qubits.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="ff9ca-158">Általánosságban elmondható, hogy a hívás a következővel van ellátva `Controlled` , és a Műveleti argumentumok a következőképpen változnak:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="ff9ca-159">`Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="ff9ca-160">Vegye figyelembe, hogy a vezérlő qubits tömbként kell megadni, még akkor is, ha az egyetlen qubit.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="ff9ca-161">A után `H` láthatjuk, hogy a következő kapuk az `R1` első qubit eljáró kapuk (és a második/harmadik által vezérelt):</span><span class="sxs-lookup"><span data-stu-id="ff9ca-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="ff9ca-162">Ezeket a következővel hívjuk</span><span class="sxs-lookup"><span data-stu-id="ff9ca-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="ff9ca-163">Vegye figyelembe, hogy a [`PI()`](xref:microsoft.quantum.math.pi) függvényt a [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) névtérből használjuk a PI radiánban kifejezett rotációk definiálásához.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="ff9ca-164">Emellett a `Double` következőt osztjuk (például `2.0` ), mert egy egész számmal való osztás `2` hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="ff9ca-165">`R1(π/2)`és `R1(π/4)` egyenértékűek a `S` és a `T` műveletekkel (a-ben is `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="ff9ca-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="ff9ca-166">A kapcsolódó `H` műveletek és a vezérelt rotációk alkalmazása után a második és a harmadik qubits:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="ff9ca-167">[`SWAP`](xref:microsoft.quantum.intrinsic.swap)az áramkör betöltéséhez csak egy kaput kell alkalmazni:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="ff9ca-168">Erre azért van szükség, mert a Quantum Fourier-transzformáció természete fordított sorrendben jeleníti meg a qubits, így a Swapek lehetővé teszik a rutinok zökkenőmentes integrálását a nagyobb algoritmusokra.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="ff9ca-169">Ezért befejeztük a Quantum Fourier-transzformáció qubit műveletének írását a Q # műveletbe:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="ff9ca-170">De nem hívhatunk meg egy napot.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="ff9ca-171">A qubits a {0} (z) $ \ket $ állapotban voltak, amikor kiosztottuk őket, és hasonlóan az életben is, a Q #-ban ugyanúgy kell elhagyni a dolgokat, ahogy azt találtuk (vagy még jobb!).</span><span class="sxs-lookup"><span data-stu-id="ff9ca-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="ff9ca-172">Qubits felszabadítása</span><span class="sxs-lookup"><span data-stu-id="ff9ca-172">Deallocate qubits</span></span>

<span data-ttu-id="ff9ca-173">A [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) művelet elvégzése előtt ismét meghívjuk a művelet utáni állapotot, végül pedig [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) a qubit-regisztrációra, hogy alaphelyzetbe állítsa a qubits $ \ket $-re a következő {0} művelet végrehajtása előtt:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="ff9ca-174">Ha azt szeretné, hogy az összes fel nem foglalt qubits legyen explicit módon beállítva a $ \ket $ értékre, {0} a Q # alapszintű funkciója, mivel lehetővé teszi, hogy más műveletek pontosan megismerjék az állapotukat, amikor megkezdik az azonos qubits (a szűkös erőforrás) használatát.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="ff9ca-175">Ez azt is biztosítja, hogy a rendszer semmilyen más qubits ne legyen összekeverve.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="ff9ca-176">Ha az alaphelyzetbe állítást a foglalási blokk végén nem hajtja végre, a rendszer `using` futásidejű hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="ff9ca-177">A teljes Q # fájlnak így kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-177">Your full Q# file should now look like this:</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


<span data-ttu-id="ff9ca-178">A Q # fájl és a művelet befejezése után a Quantum program készen áll a meghívni és szimulálni.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="ff9ca-179">A program végrehajtása</span><span class="sxs-lookup"><span data-stu-id="ff9ca-179">Execute the program</span></span>

<span data-ttu-id="ff9ca-180">Miután meghatározta a Q # műveletet egy `.qs` fájlban, most meg kell hívni a műveletet, és meg kell figyelni a visszaadott klasszikus adattípusokat.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="ff9ca-181">Egyelőre nem ad vissza semmit (ne felejtse el, hogy a fent megadott művelet visszaadja `Unit` a műveletet), de ha később módosítjuk a Q # műveletet, hogy a mérési eredmények tömbjét adja vissza ( `Result[]` ), ezt fogjuk kezelni.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="ff9ca-182">Míg a Q # program a híváshoz használt környezetek között mindenütt elérhető, ennek a módja természetesen eltérő lesz.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="ff9ca-183">Ennek megfelelően egyszerűen kövesse a beállításnak megfelelő lapon található utasításokat: a Q # parancssori alkalmazásban, vagy egy, a Pythonban vagy a C#-ban található gazda program használatával.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="ff9ca-184">Parancssor</span><span class="sxs-lookup"><span data-stu-id="ff9ca-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="ff9ca-185">A Q # program parancssorból való futtatásához csak kis módosításra van szükség a Q # fájlra.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="ff9ca-186">Egyszerűen vegyen fel `@EntryPoint()` egy sort a művelet definícióját megelőzően:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="ff9ca-187">A program futtatásához nyissa meg a terminált a projekt mappájában, és írja be a következőt:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="ff9ca-188">Végrehajtáskor a `Message` - `DumpMachine` konzolon az alábbi és kimeneteket kell látnia.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="ff9ca-189">Python</span><span class="sxs-lookup"><span data-stu-id="ff9ca-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="ff9ca-190">Hozzon létre egy Python-gazda fájlt: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="ff9ca-191">A gazda fájl a következőképpen lett kiépítve:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="ff9ca-192">Először importáljuk a `qsharp` modult, amely a Q # együttműködési képességhez regisztrálja a modul betöltőjét.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="ff9ca-193">Ez lehetővé teszi, hogy a q # névterek (például a `NamespaceQFT` q # fájlban definiált) Python-modulokként jelenjenek meg, amelyből a q # műveletei importálhatók.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="ff9ca-194">Ezután importálja a Q # azon műveleteit, amelyeket a rendszer közvetlenül meghív---ebben az esetben: `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="ff9ca-195">Csak a beléptetési pontot kell importálni a Q # programba (azaz _nem_ a ( `H` z `R1` ) és a (z).</span><span class="sxs-lookup"><span data-stu-id="ff9ca-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="ff9ca-196">A Q # műveletek vagy függvények szimulálása esetén az űrlap használatával `<Q#callable>.simulate(<args>)` futtassa őket a `QuantumSimulator()` célszámítógépen.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff9ca-197">Ha azt szeretnénk, hogy egy másik gépen, például a-ben hívjuk a műveletet, `ResourceEstimator()` egyszerűen használjuk a következőt: `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="ff9ca-198">Általánosságban elmondható, hogy a Q # műveletei a futtatott gépektől függetlenek, de bizonyos funkciók, például `DumpMachine` eltérően viselkednek.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="ff9ca-199">A szimuláció végrehajtásakor a művelet hívása a Q # fájlban meghatározott értékeket fogja visszaadni.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="ff9ca-200">Egyelőre nem tért vissza, de később láthatjuk az értékek hozzárendelésének és feldolgozásának példáját.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="ff9ca-201">A kezünkben és a klasszikusan megjelenő eredményekkel bármit megtehetünk, amit szeretne.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="ff9ca-202">A teljes `host.py` fájlnak a következőnek kell lennie:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="ff9ca-203">Futtassa a Python-fájlt, és nyomtassa ki a konzolon az `Message` `DumpMachine` alábbi és kimenetek láthatók.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="ff9ca-204">C#</span><span class="sxs-lookup"><span data-stu-id="ff9ca-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="ff9ca-205">A [telepítési útmutatóban](xref:microsoft.quantum.install.cs)szereplő utasításokat követve hozzon létre egy C#-gazdagépet, és nevezze át a következőre: `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="ff9ca-206">A C#-gazdagép négy részből áll:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="ff9ca-207">Kvantumszimulátor létrehozása.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="ff9ca-208">Az alábbi kódban ez a változó `qsim` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="ff9ca-209">A kvantumalgoritmushoz szükséges összes argumentum kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="ff9ca-210">Ebben a példában nincs ilyen.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-210">There are none in this example.</span></span>
3. <span data-ttu-id="ff9ca-211">A kvantumalgoritmus futtatása.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="ff9ca-212">Mindegyik Q#-művelet létrehoz egy azonos nevű C#-osztályt.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="ff9ca-213">Ez az osztály olyan `Run` metódussal rendelkezik, amely **aszinkron módon** hajtja végre a műveletet.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="ff9ca-214">A végrehajtás azért aszinkron módú, mert a tényleges hardveren végzett végrehajtás aszinkron módon fog történni.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="ff9ca-215">Mivel a `Run` metódus aszinkron módon van meghívva, a `Wait()` metódust hívjuk. Ez a művelet addig blokkolja a végrehajtást, amíg a feladat befejeződik, és szinkron módon visszaadja az eredményt.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="ff9ca-216">Dolgozza fel a művelet visszaadott eredményét.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="ff9ca-217">Egyelőre a művelet nem ad vissza semmit.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-217">For now, the operation returns nothing.</span></span>


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
<span data-ttu-id="ff9ca-218">Futtassa az alkalmazást, és a kimenetnek meg kell egyeznie az alábbi értékkel.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="ff9ca-219">Egy billentyű lenyomása után a program bezárul.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-219">The program will exit after you press a key.</span></span>
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

<span data-ttu-id="ff9ca-220">Ha a teljes állapotú szimulátorra hívja fel a hívást, a a `DumpMachine()` Quantum State wavefunction adatforrásként-ábrázolását adja meg.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="ff9ca-221">Egy $n $-qubit rendszer lehetséges állapotai a $2 ^ n $ számítási alapú állapotok szerint jeleníthetők meg, amelyek mindegyike egy megfelelő összetett együtthatóval (egyszerűen egy amplitúdóval és egy szakasszal) rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="ff9ca-222">A számítási állapot megfelel az összes lehetséges bináris sztringnek, $n $---, amely a qubit-állapotok összes lehetséges kombinációja $ \ket {0} $ és $ \ket {1} $, ahol az egyes bináris számjegyek egy adott qubit felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="ff9ca-223">Az első sorban a megfelelő qubits azonosítóit tartalmazó megjegyzés szerepel a jelentős sorrendben.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="ff9ca-224">A Qubit a `2` "legjelentősebb" érték azt jelenti, hogy az alapul szolgáló \ket{i} $ bináris ábrázolásban a Qubit állapota `2` a bal szélső számjegynek felel meg.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="ff9ca-225">Például a $ \ket {6} = \ket {110} $ a qubits és a $ `2` `1` \ket {1} $ és a qubit $ `0` \ket {0} $ értéket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="ff9ca-226">A többi sor a kiinduló valószínűségi amplitúdót írja le a \ket{i} $ és a poláris formátumban egyaránt.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="ff9ca-227">A bemeneti állapot első sorában a $ \ket {000} $:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="ff9ca-228">**`|0>:`** Ez a sor a `0` számítási alap állapotnak felel meg (mivel a kezdeti állapot utáni kiosztása $ \ket {000} $ volt, azt várnánk, hogy ez az egyetlen olyan állapot, amelynek a valószínűségi amplitúdója ezen a ponton).</span><span class="sxs-lookup"><span data-stu-id="ff9ca-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="ff9ca-229">**`1.000000 +  0.000000 i`**: a valószínűségi amplitúdója Descartes formátumban.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="ff9ca-230">**` == `**: a `equal` jel elválasztja mindkét egyenértékű ábrázolást.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="ff9ca-231">**`********************`**: A magnitúdó grafikus ábrázolása, amelynek száma arányos az `*` állapot-vektor mérésének valószínűségével.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="ff9ca-232">**`[ 1.000000 ]`**: a magnitúdó numerikus értéke</span><span class="sxs-lookup"><span data-stu-id="ff9ca-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="ff9ca-233">**`    ---`**: Az amplitúdó fázisának grafikus ábrázolása.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="ff9ca-234">**`[ 0.0000 rad ]`**: a fázis numerikus értéke (radiánban).</span><span class="sxs-lookup"><span data-stu-id="ff9ca-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="ff9ca-235">A magnitúdó és a fázis is grafikus ábrázolással jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="ff9ca-236">A magnitúdó ábrázolása egyszerű: megmutatja, hogy egy sáv `*` , annál nagyobb a valószínűsége, annál nagyobb lesz a sáv.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="ff9ca-237">A fázisban tekintse meg a DumpMachine szakaszt [itt](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions) a lehetséges szimbólum-ábrázolások számára a szög tartományai alapján.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-237">For the phase, see the DumpMachine section [here](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="ff9ca-238">A kinyomtatott kimenet tehát azt szemlélteti, hogy a programozott kapuk átalakították az állapotukat</span><span class="sxs-lookup"><span data-stu-id="ff9ca-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="ff9ca-239">$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="ff9ca-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="ff9ca-240">erre:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-240">to</span></span> 

<span data-ttu-id="ff9ca-241">$ $ \begin{align} \ket{\psi} \_ {Final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ff9ca-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="ff9ca-242">Ez pontosan a 3 qubit Fourier-transzformáció viselkedését képezi.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="ff9ca-243">Ha kíváncsi a más bemeneti állapotokra is, javasoljuk, hogy játsszon a qubit-műveletek alkalmazásával a transzformáció előtt.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="ff9ca-244">Mérések hozzáadása</span><span class="sxs-lookup"><span data-stu-id="ff9ca-244">Adding measurements</span></span>

<span data-ttu-id="ff9ca-245">Sajnos a kvantummechanika sarokköve azt jelzi, hogy egy valódi Quantum rendszernek nem lehet ilyen `DumpMachine` funkciója.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="ff9ca-246">Ehelyett a mérések segítségével kell kinyerni az adatokat, amelyek általánosságban nem csak a teljes kvantum-állapotot biztosítják, de a rendszer is jelentősen megváltoztatható.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="ff9ca-247">Számos kvantum-mérés létezik, de az alapszintű: az egyetlen qubits kivetítéses mérésekre koncentrálunk.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="ff9ca-248">A mérések egy adott alapon (például a $ \{ \ket {0} , \ket {1} \} $) számított érték alapján a qubit-állapotot a rendszer az adott állapotban mérte meg,---így megsemmisíti a kettő közötti felfekvést.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="ff9ca-249">A Q # programon belüli mérések megvalósításához a `M` (from) műveletet használjuk `Microsoft.Quantum.Intrinsic` , amely egy `Result` típust ad vissza.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="ff9ca-250">Először is módosítjuk a `Perform3QubitQFT` műveletet, hogy a függvény helyett a mérési eredmények egy tömbjét adják vissza `Result[]` `Unit` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="ff9ca-251">Tömb definiálása és inicializálása `Result[]`</span><span class="sxs-lookup"><span data-stu-id="ff9ca-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="ff9ca-252">A qubits (azaz az utasítás előtt) lefoglalása előtt `using` deklaráljuk és kössük ezt a hossz-3 tömböt (egyet `Result` az egyes qubit):</span><span class="sxs-lookup"><span data-stu-id="ff9ca-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="ff9ca-253">A `mutable` `resultArray` megjelenő kulcsszó lehetővé teszi, hogy a változó később a kódban legyen felkötve---például a mérési eredmények hozzáadásakor.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="ff9ca-254">Mérések végrehajtása `for` hurokban és eredmények hozzáadása a tömbhöz</span><span class="sxs-lookup"><span data-stu-id="ff9ca-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="ff9ca-255">A blokkon belüli Fourier-transzformációs műveletek után `using` szúrja be a következő kódot:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="ff9ca-256">A tömbben [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) hívott függvény (például a qubits tömbje `qs` ) a tömbben lévő indexek tartományát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="ff9ca-257">Itt használjuk a `for` hurokban, hogy szekvenciálisan mérjük az egyes qubit az utasítás használatával `M(qs[i])` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="ff9ca-258">Az egyes mért `Result` típusok ( `Zero` vagy `One` ) bekerülnek a megfelelő index helyére `resultArray` egy Update-and-reassign utasítással.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="ff9ca-259">Ennek az utasításnak a szintaxisa egyedi a Q # típushoz, de megfelel a hasonló változó ismételt hozzárendelésének, `resultArray[i] <- M(qs[i])` más nyelveken, például F # és R nyelven.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="ff9ca-260">A kulcsszó `set` mindig a használatával kötött változók ismételt hozzárendelésére szolgál `mutable` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="ff9ca-261">Visszatérési`resultArray`</span><span class="sxs-lookup"><span data-stu-id="ff9ca-261">Return `resultArray`</span></span>

<span data-ttu-id="ff9ca-262">Mind a három qubits, mind a hozzá tartozó eredmények alapján a `resultArray` qubits alaphelyzetbe állítása és felszabadítása is biztonságos.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="ff9ca-263">A `using` blokk bezárását követően szúrja be a következőt</span><span class="sxs-lookup"><span data-stu-id="ff9ca-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="ff9ca-264">végső soron a művelet eredményét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="ff9ca-265">A mérés következményeinek megértése</span><span class="sxs-lookup"><span data-stu-id="ff9ca-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="ff9ca-266">Módosítsa a függvények elhelyezését `DumpMachine` , hogy az állapotot a mérések előtt és után adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="ff9ca-267">A végső műveleti kódnak a következőhöz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-267">The final operation code should look like:</span></span> 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

<span data-ttu-id="ff9ca-268">Ha a parancssorból dolgozik, a visszaadott tömb egyszerűen a végrehajtás végén közvetlenül a konzolra lesz kinyomtatva.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="ff9ca-269">Ellenkező esetben frissítse a gazdagép programját a visszaadott tömb feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="ff9ca-270">Parancssor</span><span class="sxs-lookup"><span data-stu-id="ff9ca-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="ff9ca-271">Ha jobban meg szeretné ismerni a visszaadott tömböt, amely a konzolon lesz kinyomtatva, a Q # fájlban is hozzáadhat egy másikat, `Message` közvetlenül a következő `return` utasítás előtt:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="ff9ca-272">Futtassa a projektet, és a kimenetnek a következőhöz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-272">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[<span data-ttu-id="ff9ca-273">Python</span><span class="sxs-lookup"><span data-stu-id="ff9ca-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="ff9ca-274">Frissítse Python-programját a következőre:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-274">Update your Python program to the following:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

<span data-ttu-id="ff9ca-275">Futtassa a fájlt, és a kimenetnek a következőhöz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-275">Run the file, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[<span data-ttu-id="ff9ca-276">C#</span><span class="sxs-lookup"><span data-stu-id="ff9ca-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="ff9ca-277">Most, hogy a művelet visszaad egy eredményt, cserélje le a metódust a `Wait()` tulajdonság beolvasására `Result` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="ff9ca-278">Ez továbbra is ugyanazokat a szinkronkat hajtja végre, mint korábban, és ezt az értéket közvetlenül a változóhoz kötheti `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="ff9ca-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="ff9ca-279">Futtassa a projektet, és a kimenetnek a következőhöz hasonlóan kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-279">Run the project, and your output should look similar to the following:</span></span>

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

<span data-ttu-id="ff9ca-280">Ez a kimenet néhány különböző dolgot mutat be:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="ff9ca-281">A visszaadott eredménynek az előzetes méréssel való összevetése `DumpMachine` egyértelműen _nem_ mutatja be az QFT utáni pozíciót az alapállapotok alapján.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="ff9ca-282">A mérések csak egyetlen alap állapotot adnak vissza, amelynek valószínűségét az adott állapot amplitúdója határozza meg a rendszer wavefunction.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="ff9ca-283">Az utólagos mérés után azt `DumpMachine` látjuk, hogy a mérés magára az állapotra _változik_ , és az alapszintű, a mért értéknek megfelelő egységes állapotba állítja azt.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="ff9ca-284">Ha többször is megismétli ezt a műveletet, akkor az eredmények statisztikái megkezdik a QFT-állapot ugyanilyen súlyozott feltételét, amely az egyes lövések véletlenszerű eredményét idézi elő.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="ff9ca-285">_Azonban_a nem hatékony és még mindig nem tökéletes, ezért csak az alapállapotok relatív amplitúdóit fogja reprodukálni, nem a közöttük lévő relatív fázisokat.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="ff9ca-286">Az utóbbi nem jelent problémát ebben a példában, de a relatív fázisok akkor jelennek meg, ha a QFT összetettebb inputot kap a $ \ket {000} $ értéknél.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="ff9ca-287">Részleges mérések</span><span class="sxs-lookup"><span data-stu-id="ff9ca-287">Partial measurements</span></span> 
<span data-ttu-id="ff9ca-288">Annak megismeréséhez, hogy a regisztráció egyes qubits milyen hatással lehetnek a rendszerek állapotára, próbálja meg hozzáadni a következőt a `for` hurokon belül a mérési sor után:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="ff9ca-289">Vegye figyelembe, hogy a `IntAsString` hozzáadni kívánt függvény eléréséhez hozzá kell adnia</span><span class="sxs-lookup"><span data-stu-id="ff9ca-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="ff9ca-290">a többi névtér- `open` utasítással.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="ff9ca-291">Az eredményül kapott kimenetben látni fogja a fokozatos kivetítést az alterületekre, ahogy az egyes qubit mérik.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-q-libraries"></a><span data-ttu-id="ff9ca-292">A Q # kódtárak használata</span><span class="sxs-lookup"><span data-stu-id="ff9ca-292">Use the Q# libraries</span></span>
<span data-ttu-id="ff9ca-293">Ahogy azt a bevezetésben is említettük, a Q # nagyobb teljesítményének köszönhetően a tény, hogy lehetővé teszi, hogy elvonta az egyes qubits foglalkozó gondokat.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="ff9ca-294">Ha teljes körű, alkalmazható kvantum-programokat szeretne fejleszteni, ne aggódjon, hogy egy `H` adott művelet egy adott rotáció előtt vagy után leáll-e.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="ff9ca-295">A Q # függvénytárak tartalmazzák a [QFT](xref:microsoft.quantum.canon.qft) műveletet, amely egyszerűen elvégezhető, és tetszőleges számú qubits alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="ff9ca-296">A kipróbáláshoz adjon meg egy új műveletet a Q # fájlban, amelynek tartalma megegyezik `Perform3QubitQFT` , de az elsőtől `H` a `SWAP` helyébe két egyszerű vonal lép:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="ff9ca-297">Az első sor egyszerűen létrehoz egy [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) kifejezést a qubits lefoglalt tömbből, `qs` amely a [QFT](xref:microsoft.quantum.canon.qft) művelet argumentumként való végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="ff9ca-298">Ez megfelel a regisztrációban szereplő qubits index szerinti rendezésének.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="ff9ca-299">Ahhoz, hogy hozzáférhessenek ezekhez a műveletekhez, adja hozzá a `open` megfelelő névterekhez tartozó utasításokat a Q # fájl elején:</span><span class="sxs-lookup"><span data-stu-id="ff9ca-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="ff9ca-300">Most állítsa be úgy a gazda programot, hogy meghívja az új művelet nevét (pl. `PerformIntrinsicQFT` ), és adjon neki egy örvényt.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="ff9ca-301">Ha meg szeretné tekinteni a Q # Library-műveletek használatának valódi előnyeit, módosítsa a qubits számát a következőre `3` :</span><span class="sxs-lookup"><span data-stu-id="ff9ca-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="ff9ca-302">Így alkalmazhatja a megfelelő QFT az adott számú qubits, anélkül, hogy aggódnia kellene az új `H` műveletek és Forgások az egyes qubit.</span><span class="sxs-lookup"><span data-stu-id="ff9ca-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="ff9ca-303">Vegye figyelembe, hogy a Quantum Simulator exponenciálisan több időt vesz igénybe a qubits számának növelésével,---pontosan miért várjuk a valódi kvantum-hardvereket!</span><span class="sxs-lookup"><span data-stu-id="ff9ca-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













