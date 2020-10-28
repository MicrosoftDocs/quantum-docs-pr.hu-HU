---
title: 'A felakadás megismerése :::no-loc(Q#):::'
description: 'Megtudhatja, hogyan írhat Quantum programot a alkalmazásban :::no-loc(Q#)::: . Bell-állapotot jelző alkalmazás fejlesztése a Quantum Development Kit (QDK) használatával'
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 7a1a49e18ac9330ca6e3cc89b3e58c96eccb91db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691668"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="0ad52-104">Oktatóanyag: Összefonódások megismerése Q\# nyelven</span><span class="sxs-lookup"><span data-stu-id="0ad52-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="0ad52-105">Ebben az oktatóanyagban bemutatjuk, hogyan írhat olyan :::no-loc(Q#)::: programot, amely manipulálja és méri a qubits, és bemutatja a Felfekvés és a felakadás hatásait.</span><span class="sxs-lookup"><span data-stu-id="0ad52-105">In this tutorial, we show you how to write a :::no-loc(Q#)::: program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="0ad52-106">Írni fog egy Bell nevű alkalmazást a kvantum-összefonódás szemléltetése céljából.</span><span class="sxs-lookup"><span data-stu-id="0ad52-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="0ad52-107">A Bell név a Bell-állapotokra utal. Ezek két qubit konkrét kvantumállapotát jelentik, amelyekkel szemléltethetők a szuperpozíció és a kvantum-összefonódás legegyszerűbb példái.</span><span class="sxs-lookup"><span data-stu-id="0ad52-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="0ad52-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="0ad52-108">Pre-requisites</span></span>

<span data-ttu-id="0ad52-109">Ha készen áll a kódolásra, először végezze el a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0ad52-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="0ad52-110">[Telepítse](xref:microsoft.quantum.install) a Quantum Development Kit-t az előnyben részesített nyelvi és fejlesztési környezet használatával.</span><span class="sxs-lookup"><span data-stu-id="0ad52-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="0ad52-111">Ha a QDK már telepítve van, győződjön meg arról, hogy a legújabb verzióra van [frissítve](xref:microsoft.quantum.update).</span><span class="sxs-lookup"><span data-stu-id="0ad52-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="0ad52-112">A QDK telepítése nélkül is követheti az elbeszélést, így áttekintheti a :::no-loc(Q#)::: programozási nyelv áttekintését és a kvantum-számítástechnika első fogalmait.</span><span class="sxs-lookup"><span data-stu-id="0ad52-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the :::no-loc(Q#)::: programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="0ad52-113">Ebből az oktatóanyagból az alábbiakat sajátíthatja el:</span><span class="sxs-lookup"><span data-stu-id="0ad52-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="0ad52-114">Műveletek létrehozása és egyesítése a Q-ban\#</span><span class="sxs-lookup"><span data-stu-id="0ad52-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="0ad52-115">Hozzon létre olyan műveleteket, amelyek a qubits a helyükre helyezik, összekeverik és mérik.</span><span class="sxs-lookup"><span data-stu-id="0ad52-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="0ad52-116">Bemutatja a kvantum-felakadás egy :::no-loc(Q#)::: program futtatásával szimulátorban.</span><span class="sxs-lookup"><span data-stu-id="0ad52-116">Demonstrate quantum entanglement with a :::no-loc(Q#)::: program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="0ad52-117">A qubit viselkedésének bemutatása a QDK</span><span class="sxs-lookup"><span data-stu-id="0ad52-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="0ad52-118">Míg a hagyományos bit egyetlen bináris értéket hordoz, ami 0 vagy 1 lehet, a [qubit](xref:microsoft.quantum.glossary#qubit) állapota a 0 és az 1 érték közötti **szuperpozícióban** is lehet.</span><span class="sxs-lookup"><span data-stu-id="0ad52-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="0ad52-119">Elméletileg a qubit állapota absztrakt (más néven vektoros) térben is megtekinthető.</span><span class="sxs-lookup"><span data-stu-id="0ad52-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="0ad52-120">A qubit-állapot lehet a lehetséges irányok bármelyike.</span><span class="sxs-lookup"><span data-stu-id="0ad52-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="0ad52-121">A két **klasszikus állapot** az a két irány, amelyek a 0 érték mérésének 100%-os esélyét és az 1 érték mérésének 100%-os esélyét jelentik.</span><span class="sxs-lookup"><span data-stu-id="0ad52-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="0ad52-122">A mérés ténye egy bináris eredményt ad, és megváltoztatja a qubit állapotát.</span><span class="sxs-lookup"><span data-stu-id="0ad52-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="0ad52-123">A mérés bináris értéket állít elő (0 vagy 1).</span><span class="sxs-lookup"><span data-stu-id="0ad52-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="0ad52-124">A qubit a szuperpozícióból (amely bármilyen irányú lehet) az egyik klasszikus állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="0ad52-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="0ad52-125">Ezt követően ugyanannak a mérésnek a megismétlése – ha időközben nem végeztünk el semmilyen más műveletet – ugyanazt a bináris eredményt adja.</span><span class="sxs-lookup"><span data-stu-id="0ad52-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="0ad52-126">Több qubit [**össze is fonható**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="0ad52-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="0ad52-127">Ha az összefonódott qubitek egyikéről mérést készítünk, a másik/többi állapotáról is információt kapunk.</span><span class="sxs-lookup"><span data-stu-id="0ad52-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="0ad52-128">Most már készen áll annak bemutatására, hogy :::no-loc(Q#)::: ez hogyan fejezi ki ezt a viselkedést.</span><span class="sxs-lookup"><span data-stu-id="0ad52-128">Now, we're ready to demonstrate how :::no-loc(Q#)::: expresses this behavior.</span></span>  <span data-ttu-id="0ad52-129">A lehető legegyszerűbb programmal kezd, és azt építi fel a kvantum-szuperpozíció és a kvantum-összefonódás bemutatásához.</span><span class="sxs-lookup"><span data-stu-id="0ad52-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="0ad52-130">Projekt létrehozása :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="0ad52-130">Creating a :::no-loc(Q#)::: project</span></span>

<span data-ttu-id="0ad52-131">Első lépésként hozzon létre egy új :::no-loc(Q#)::: projektet.</span><span class="sxs-lookup"><span data-stu-id="0ad52-131">The first thing we have to do is to create a new :::no-loc(Q#)::: project.</span></span> <span data-ttu-id="0ad52-132">Ebben az oktatóanyagban ezt a környezetet fogjuk használni a [ :::no-loc(Q#)::: vs Code-alkalmazások](xref:microsoft.quantum.install.standalone)alapján.</span><span class="sxs-lookup"><span data-stu-id="0ad52-132">In this tutorial we are going to use the environment based on [:::no-loc(Q#)::: applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="0ad52-133">Új projekt létrehozásához a VS Code-ban:</span><span class="sxs-lookup"><span data-stu-id="0ad52-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="0ad52-134">Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **:::no-loc(Q#):::: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0ad52-134">Click **View** -> **Command Palette** and select **:::no-loc(Q#):::: Create New Project** .</span></span>
2. <span data-ttu-id="0ad52-135">Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.</span><span class="sxs-lookup"><span data-stu-id="0ad52-135">Click **Standalone console application** .</span></span>
3. <span data-ttu-id="0ad52-136">Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0ad52-136">Navigate to the location to save the project and click **Create Project** .</span></span>
4. <span data-ttu-id="0ad52-137">A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.</span><span class="sxs-lookup"><span data-stu-id="0ad52-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="0ad52-138">Ebben az esetben a projektet hívjuk `Bell` .</span><span class="sxs-lookup"><span data-stu-id="0ad52-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="0ad52-139">Ez két fájlt hoz létre: `Bell.csproj` a projektfájlt és egy olyan `Program.qs` alkalmazás sablonját, :::no-loc(Q#)::: amelyet az alkalmazás írásához fogunk használni.</span><span class="sxs-lookup"><span data-stu-id="0ad52-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a :::no-loc(Q#)::: application that we will use to write our application.</span></span> <span data-ttu-id="0ad52-140">A tartalomnak a `Program.qs` következőket kell tartalmaznia:</span><span class="sxs-lookup"><span data-stu-id="0ad52-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="0ad52-141">A Q- \# alkalmazás írása</span><span class="sxs-lookup"><span data-stu-id="0ad52-141">Write the Q\# application</span></span>
 
<span data-ttu-id="0ad52-142">Célunk, hogy előkészítsünk két qubits egy konkrét kvantum-állapotban, amely azt mutatja be, hogyan lehet a qubits-ben működni, :::no-loc(Q#)::: hogy megváltoztassák az állapotukat, és bemutatják a Felfekvés és a felakadás hatását.</span><span class="sxs-lookup"><span data-stu-id="0ad52-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with :::no-loc(Q#)::: to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="0ad52-143">A qubit-állapotok, a műveletek és a mérések bevezetéséhez egy darabot hozunk létre.</span><span class="sxs-lookup"><span data-stu-id="0ad52-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="0ad52-144">Qubit inicializálása mérés használatával</span><span class="sxs-lookup"><span data-stu-id="0ad52-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="0ad52-145">Az alábbi kódrészletben bemutatjuk, hogyan dolgozhat a qubits a alkalmazásban :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="0ad52-145">In the first code snippet below, we show you how to work with qubits in :::no-loc(Q#):::.</span></span>  <span data-ttu-id="0ad52-146">Két műveletet fogunk bevezetni [`M`](xref:Microsoft.Quantum.Intrinsic.m) , [`X`](xref:Microsoft.Quantum.Intrinsic.X) amely átalakítja a qubit állapotát.</span><span class="sxs-lookup"><span data-stu-id="0ad52-146">We’ll introduce two operations, [`M`](xref:Microsoft.Quantum.Intrinsic.m) and [`X`](xref:Microsoft.Quantum.Intrinsic.X) that transform the state of a qubit.</span></span> <span data-ttu-id="0ad52-147">Ebben a kódrészletben meghatározunk egy `SetQubitState` műveletet, amelynek egyik paramétere egy qubit, a másik pedig a `desired`, amely a qubit kívánt állapotát jelöli.</span><span class="sxs-lookup"><span data-stu-id="0ad52-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="0ad52-148">A `SetQubitState` művelet elvégez egy mérést a qubiten az `M` művelet használatával.</span><span class="sxs-lookup"><span data-stu-id="0ad52-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="0ad52-149">A-ben :::no-loc(Q#)::: a qubit-mérések mindig a vagy a értéket adja vissza `Zero` `One` .</span><span class="sxs-lookup"><span data-stu-id="0ad52-149">In :::no-loc(Q#):::, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="0ad52-150">Ha a mérés olyan értéket ad vissza, amely nem egyenlő a kívánt értékkel, a `SetQubitState` "megfordítja" a qubit, azaz egy `X` műveletet futtat, amely a qubit állapotot olyan új állapotba változtatja, amelyben a visszaadott mérés valószínűsége `Zero` és fordított állapota `One` történik.</span><span class="sxs-lookup"><span data-stu-id="0ad52-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="0ad52-151">Így mindig a `SetQubitState` kívánt állapotba helyezi a cél qubit.</span><span class="sxs-lookup"><span data-stu-id="0ad52-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="0ad52-152">Cserélje le a tartalmát a `Program.qs` következő kódra:</span><span class="sxs-lookup"><span data-stu-id="0ad52-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="0ad52-153">Most már meghívható ez a művelet, hogy egy qubitet egy klasszikus állapotba állítson, és az esetek 100%-ában kizárólag `Zero` vagy `One` eredményt adjon vissza.</span><span class="sxs-lookup"><span data-stu-id="0ad52-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="0ad52-154">A `Zero` és az `One` állandók, amelyek a qubit mérésének két lehetséges eredményét jelölik.</span><span class="sxs-lookup"><span data-stu-id="0ad52-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="0ad52-155">A `SetQubitState` művelet elvégzi a qubit mérését.</span><span class="sxs-lookup"><span data-stu-id="0ad52-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="0ad52-156">Ha a qubit a kívánt állapotban van, `SetQubitState` hagyja békén, ellenkező esetben a művelet futtatásával `X` módosítjuk a qubit állapotát a kívánt állapotra.</span><span class="sxs-lookup"><span data-stu-id="0ad52-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="0ad52-157">Tudnivalók a :::no-loc(Q#)::: műveletekről</span><span class="sxs-lookup"><span data-stu-id="0ad52-157">About :::no-loc(Q#)::: operations</span></span>

<span data-ttu-id="0ad52-158">A :::no-loc(Q#)::: művelet egy kvantum-alrutin.</span><span class="sxs-lookup"><span data-stu-id="0ad52-158">A :::no-loc(Q#)::: operation is a quantum subroutine.</span></span> <span data-ttu-id="0ad52-159">Ez egy meghívásos rutin, amely más kvantum-műveletekre irányuló hívásokat is tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="0ad52-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="0ad52-160">A műveletek argumentumai rekordként vannak meghatározva, zárójelek között.</span><span class="sxs-lookup"><span data-stu-id="0ad52-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="0ad52-161">A művelet visszatérési típusa a kettőspont után van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="0ad52-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="0ad52-162">Ebben az esetben a `SetQubitState` művelet nem tartalmaz visszatérési típust, ezért a rendszer visszatérként jelöli meg `Unit` .</span><span class="sxs-lookup"><span data-stu-id="0ad52-162">In this case, the `SetQubitState` operation has no return type, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="0ad52-163">Ez egyenértékű az :::no-loc(Q#)::: `unit` F #-ban, amely nagyjából a C#-ban van, `void` és egy üres rekord a Pythonban (amelyet `()` a Type hint jelöl `Tuple[()]` ).</span><span class="sxs-lookup"><span data-stu-id="0ad52-163">This is the :::no-loc(Q#)::: equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="0ad52-164">Az első művelet során két Quantum műveletet használt :::no-loc(Q#)::: :</span><span class="sxs-lookup"><span data-stu-id="0ad52-164">You have used two quantum operations in your first :::no-loc(Q#)::: operation:</span></span>

* <span data-ttu-id="0ad52-165">A [`M`](xref:Microsoft.Quantum.Intrinsic.m) művelet, amely a qubit állapotát méri</span><span class="sxs-lookup"><span data-stu-id="0ad52-165">The [`M`](xref:Microsoft.Quantum.Intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="0ad52-166">A [`X`](xref:Microsoft.Quantum.Intrinsic.X) qubit állapotát tükröző művelet</span><span class="sxs-lookup"><span data-stu-id="0ad52-166">The [`X`](xref:Microsoft.Quantum.Intrinsic.X) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="0ad52-167">A kvantumműveletek átalakítják a qubitek állapotát.</span><span class="sxs-lookup"><span data-stu-id="0ad52-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="0ad52-168">Bizonyos esetekben a hagyományos logikai kapuk mintájára szokás kvantumkapukat emlegetni műveletek helyett.</span><span class="sxs-lookup"><span data-stu-id="0ad52-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="0ad52-169">Ez a szokás a kvantum-számítástechnika korai időszakából ered, amikor az algoritmusok még csupán elméleti fogalmak voltak, és diagramként vizualizálták őket, hasonlóan a klasszikus számítástechnikában használt kapcsolási rajzokhoz.</span><span class="sxs-lookup"><span data-stu-id="0ad52-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="0ad52-170">Mérési eredmények számlálása</span><span class="sxs-lookup"><span data-stu-id="0ad52-170">Counting measurement outcomes</span></span>

<span data-ttu-id="0ad52-171">Ezután a `SetQubitState` művelet hatásának szemléltetésére a rendszer hozzáad egy `TestBellState` műveletet.</span><span class="sxs-lookup"><span data-stu-id="0ad52-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="0ad52-172">Ennek a műveletnek a bemenete egy `Zero` vagy `One`. A művelet néhányszor meghívja a `SetQubitState` műveletet ezzel a bemenettel, és megszámolja, hogy a qubit mérése hányszor adott `Zero`, és hányszor `One` eredményt.</span><span class="sxs-lookup"><span data-stu-id="0ad52-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="0ad52-173">Természetesen a `TestBellState` művelet első szimulációjától egy olyan kimenetet várunk, amely azt mutatja, hogy minden `Zero` bemeneti paraméterrel rendelkező qubit a `Zero` eredményt adja vissza, és minden `One` bemeneti paraméterrel rendelkező qubit az `One` eredményt.</span><span class="sxs-lookup"><span data-stu-id="0ad52-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="0ad52-174">További bekapcsolás esetén a rendszer hozzáad egy kódot, amely `TestBellState` bemutatja a felfekvést és a felakadás.</span><span class="sxs-lookup"><span data-stu-id="0ad52-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="0ad52-175">Adja hozzá az alábbi műveletet a `SetQubitState` fájlhoz, a névtéren belül, a `Program.qs` művelet végén:</span><span class="sxs-lookup"><span data-stu-id="0ad52-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="0ad52-176">Vegye figyelembe, hogy a `return` ( `Message` ) [Microsoft. Quantum. belső. Message] függvénnyel egy, a-konzolon a (</span><span class="sxs-lookup"><span data-stu-id="0ad52-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="0ad52-177">Ennek a műveletnek (`TestBellState`) `count` iterációja ismétlődik, beállít egy megadott `initial` értéket egy qubiten, majd megméri (`M`) az eredményt.</span><span class="sxs-lookup"><span data-stu-id="0ad52-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="0ad52-178">Statisztikát gyűjt arról, hogy hány nulla és egy értéket mért, és visszaküldi őket a hívónak.</span><span class="sxs-lookup"><span data-stu-id="0ad52-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="0ad52-179">Még egy szükséges műveletet végrehajt.</span><span class="sxs-lookup"><span data-stu-id="0ad52-179">It performs one other necessary operation.</span></span> <span data-ttu-id="0ad52-180">Visszaállítja a qubitet egy ismert állapotra (`Zero`), mielőtt visszaadja, hogy mások is lefoglalhassák ezt a qubitet egy ismert állapotban.</span><span class="sxs-lookup"><span data-stu-id="0ad52-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="0ad52-181">Ez a `using` utasítás miatt szükséges.</span><span class="sxs-lookup"><span data-stu-id="0ad52-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="0ad52-182">A Q változók\#</span><span class="sxs-lookup"><span data-stu-id="0ad52-182">About variables in Q\#</span></span>

<span data-ttu-id="0ad52-183">Alapértelmezés szerint a változói :::no-loc(Q#)::: nem változtathatók meg; az értékük a kötés után nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="0ad52-183">By default, variables in :::no-loc(Q#)::: are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="0ad52-184">A nem módosítható változók kötése a `let` kulcsszóval jelölhető.</span><span class="sxs-lookup"><span data-stu-id="0ad52-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="0ad52-185">A műveleti argumentumok soha nem módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="0ad52-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="0ad52-186">Ha olyan változóra van szüksége, amelynek értéke módosítható (mint a `numOnes` a fenti példában), a `mutable` kulcsszóval deklarálhatja a változót.</span><span class="sxs-lookup"><span data-stu-id="0ad52-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="0ad52-187">A módosítható változók értéke a `set` utasítással módosítható.</span><span class="sxs-lookup"><span data-stu-id="0ad52-187">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="0ad52-188">A változó típusát mindkét esetben a fordító következteti ki.</span><span class="sxs-lookup"><span data-stu-id="0ad52-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="0ad52-189">:::no-loc(Q#)::: a változókhoz nem szükséges semmilyen típusú Megjegyzés.</span><span class="sxs-lookup"><span data-stu-id="0ad52-189">:::no-loc(Q#)::: doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="0ad52-190">A `using` Q utasításai\#</span><span class="sxs-lookup"><span data-stu-id="0ad52-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="0ad52-191">Az `using` utasítás szintén speciális :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="0ad52-191">The `using` statement is also special to :::no-loc(Q#):::.</span></span> <span data-ttu-id="0ad52-192">Ezzel foglalhatók le qubitek a kódblokkokhoz.</span><span class="sxs-lookup"><span data-stu-id="0ad52-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="0ad52-193">A-ben az :::no-loc(Q#)::: összes qubits dinamikusan van lefoglalva és felszabadítva, ahelyett, hogy rögzített erőforrásokkal rendelkezik egy összetett algoritmus teljes élettartama alatt.</span><span class="sxs-lookup"><span data-stu-id="0ad52-193">In :::no-loc(Q#):::, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="0ad52-194">A `using` utasítás a blokk elején foglal le qubiteket, és a blokk végén felszabadítja őket.</span><span class="sxs-lookup"><span data-stu-id="0ad52-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="0ad52-195">Futtassa a kódot a parancssorból.</span><span class="sxs-lookup"><span data-stu-id="0ad52-195">Run the code from the command prompt</span></span>

<span data-ttu-id="0ad52-196">A kód futtatásához meg kell adnia azt a fordítót, *amely* akkor fut, ha a `dotnet run` parancsot megadja.</span><span class="sxs-lookup"><span data-stu-id="0ad52-196">In order to run the code we need to tell the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="0ad52-197">Ez a fájl egyszerű módosításával történik :::no-loc(Q#)::: egy olyan vonal hozzáadásával, amely `@EntryPoint()` közvetlenül megelőzi a meghívót: a művelet ebben az `TestBellState` esetben.</span><span class="sxs-lookup"><span data-stu-id="0ad52-197">This is done with a simple change in the :::no-loc(Q#)::: file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="0ad52-198">A teljes kódnak a következőket kell tennie:</span><span class="sxs-lookup"><span data-stu-id="0ad52-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="0ad52-199">A program futtatásához meg kell adni a `count` parancssorból a és a `initial` argumentumot.</span><span class="sxs-lookup"><span data-stu-id="0ad52-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="0ad52-200">Választhatja például a következőt: `count = 1000` és `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="0ad52-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="0ad52-201">Írja be a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="0ad52-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="0ad52-202">A következő kimenetnek kell megjelennie:</span><span class="sxs-lookup"><span data-stu-id="0ad52-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="0ad52-203">Ha a-vel próbálkozik, `initial = Zero` vegye figyelembe a következőket:</span><span class="sxs-lookup"><span data-stu-id="0ad52-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="0ad52-204">Szuperpozíció előkészítése</span><span class="sxs-lookup"><span data-stu-id="0ad52-204">Prepare superposition</span></span>

<span data-ttu-id="0ad52-205">Most nézzük meg, hogyan :::no-loc(Q#)::: fejezheti be a qubits a saját pozícióban.</span><span class="sxs-lookup"><span data-stu-id="0ad52-205">Now let’s look at how :::no-loc(Q#)::: expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="0ad52-206">Emlékezzünk arra, hogy a qubitek állapota a 0 és az 1 értéket egyszerre lefedő szuperpozícióban is lehet.</span><span class="sxs-lookup"><span data-stu-id="0ad52-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="0ad52-207">Ennek eléréséhez a `Hadamard` műveletet használjuk.</span><span class="sxs-lookup"><span data-stu-id="0ad52-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="0ad52-208">Ha a qubit valamelyik klasszikus állapotban van (amikor a mérések mindig `Zero` vagy mindig `One` értéket adnak vissza), akkor a `Hadamard` vagy `H` művelet olyan állapotba helyezi a qubitet, amelyben a mérések 50%-ban `Zero` és 50%-ban `One` eredményt adnak.</span><span class="sxs-lookup"><span data-stu-id="0ad52-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="0ad52-209">Alapjában véve a qubit úgy képzelhető el, hogy félúton van a `Zero` és az `One` között.</span><span class="sxs-lookup"><span data-stu-id="0ad52-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="0ad52-210">Ilyenkor a `TestBellState` művelet szimulálása esetén azt fogjuk látni, hogy a mérések nagyjából azonos alkalommal adják ki a `Zero` és az `One` értéket.</span><span class="sxs-lookup"><span data-stu-id="0ad52-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="0ad52-211">`X` qubit állapotának tükrözése</span><span class="sxs-lookup"><span data-stu-id="0ad52-211">`X` flips qubit state</span></span>

<span data-ttu-id="0ad52-212">Először is megpróbáljuk megfordítani a qubit (ha a qubit állapotban van, `Zero` `One` és fordítva).</span><span class="sxs-lookup"><span data-stu-id="0ad52-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state it will flip to `One` and vice versa).</span></span> <span data-ttu-id="0ad52-213">Ezt úgy érhetjük el, ha végrehajtunk egy `X` műveletet, mielőtt megmérnénk az `TestBellState`-ben:</span><span class="sxs-lookup"><span data-stu-id="0ad52-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="0ad52-214">A rendszer most visszafordítja az eredményeket:</span><span class="sxs-lookup"><span data-stu-id="0ad52-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="0ad52-215">Most vizsgáljuk meg a qubits kvantum-tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="0ad52-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="0ad52-216">`H` felkészíti a felfekvést</span><span class="sxs-lookup"><span data-stu-id="0ad52-216">`H` prepares superposition</span></span>

<span data-ttu-id="0ad52-217">Mindössze le kell cserélnünk az előző futtatás `X` műveletét egy `H` vagy egy Hadamard-műveletre.</span><span class="sxs-lookup"><span data-stu-id="0ad52-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="0ad52-218">Ahelyett, hogy 0-ról 1-re teljesen átállítani a qubitet, csak félig fordítjuk át.</span><span class="sxs-lookup"><span data-stu-id="0ad52-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="0ad52-219">A `TestBellState`-ben most így néznek ki a lecserélt sorok:</span><span class="sxs-lookup"><span data-stu-id="0ad52-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="0ad52-220">Az eredmények most még érdekesebbek:</span><span class="sxs-lookup"><span data-stu-id="0ad52-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="0ad52-221">Minden méréskor egy klasszikus értéket kérünk, de a qubit félúton van 0 és 1 között, így (statisztikailag) az esetek felében 0, a másik felében 1 értéket kapunk.</span><span class="sxs-lookup"><span data-stu-id="0ad52-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="0ad52-222">Ez az úgynevezett **szuperpozíció** , és az első valódi betekintést nyújtja a kvantumállapotba.</span><span class="sxs-lookup"><span data-stu-id="0ad52-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="0ad52-223">Az összefonódás előkészítése</span><span class="sxs-lookup"><span data-stu-id="0ad52-223">Prepare entanglement</span></span>

<span data-ttu-id="0ad52-224">Most nézzük meg, hogyan :::no-loc(Q#)::: fejezi ki a qubits-k összekeverhető módjait.</span><span class="sxs-lookup"><span data-stu-id="0ad52-224">Now let’s look at how :::no-loc(Q#)::: expresses ways to entangle qubits.</span></span>
<span data-ttu-id="0ad52-225">Először is az első qubitet a kezdeti állapotba, majd a `H` művelettel szuperpozícióba kell állítanunk.</span><span class="sxs-lookup"><span data-stu-id="0ad52-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="0ad52-226">Ezután az első qubit mérése előtt egy új műveletet () használunk `CNOT` , amely a *vezérlést nem* jelenti.</span><span class="sxs-lookup"><span data-stu-id="0ad52-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT* .</span></span>  <span data-ttu-id="0ad52-227">A művelet két qubits való futtatásának eredménye a második qubit tükrözése, ha az első qubit van `One` .</span><span class="sxs-lookup"><span data-stu-id="0ad52-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="0ad52-228">Ekkor a két qubit összefonódik.</span><span class="sxs-lookup"><span data-stu-id="0ad52-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="0ad52-229">Az első qubit statisztikái nem változnak (mérés esetén 50%-os eséllyel lesz `Zero` vagy `One`), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk.</span><span class="sxs-lookup"><span data-stu-id="0ad52-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="0ad52-230">A `CNOT` összekapcsolta a két qubitet, így bármi is történik az egyikkel, ugyanaz történik a másikkal is.</span><span class="sxs-lookup"><span data-stu-id="0ad52-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="0ad52-231">Ha felcseréli a méréseket (a második qubitet mérve az első előtt), akkor is ugyanez történik.</span><span class="sxs-lookup"><span data-stu-id="0ad52-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="0ad52-232">Az első mérés eredménye véletlenszerű lesz, a második pedig mindig ugyanaz, mint amit az elsőnél kaptunk.</span><span class="sxs-lookup"><span data-stu-id="0ad52-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="0ad52-233">Első lépésként két qubits kell lefoglalni a következő helyett `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="0ad52-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="0ad52-234">Így új műveletet (`CNOT`) adhatunk hozzá a mérés (`M`) előtt a `TestBellState`-ben:</span><span class="sxs-lookup"><span data-stu-id="0ad52-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="0ad52-235">Hozzáadtunk egy másik `SetQubitState` műveletet az első qubit inicializálásához, hogy biztosan mindig `Zero` állapotban legyen indításkor.</span><span class="sxs-lookup"><span data-stu-id="0ad52-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="0ad52-236">A felszabadítása előtt alaphelyzetbe is kell állítanunk a második qubitet.</span><span class="sxs-lookup"><span data-stu-id="0ad52-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="0ad52-237">A teljes folyamatnak most így kell kinéznie:</span><span class="sxs-lookup"><span data-stu-id="0ad52-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="0ad52-238">Ha ezt lefuttatjuk, akkor pontosan ugyanazt a fifti-fifti eredményt fogjuk kapni, amit korábban is.</span><span class="sxs-lookup"><span data-stu-id="0ad52-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="0ad52-239">Minket azonban az érdekel, hogy a második qubit hogyan reagál az első mérésére.</span><span class="sxs-lookup"><span data-stu-id="0ad52-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="0ad52-240">Ez a statisztikát hozzáadjuk a `TestBellState` művelet új verziójához:</span><span class="sxs-lookup"><span data-stu-id="0ad52-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="0ad52-241">Az új visszaadott érték (`agree`) minden olyan alkalmat nyomon követ, amikor az első qubit mérési eredménye megegyezik a második kvantumbitével.</span><span class="sxs-lookup"><span data-stu-id="0ad52-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="0ad52-242">A beszerzett kód futtatása:</span><span class="sxs-lookup"><span data-stu-id="0ad52-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="0ad52-243">Ahogy az áttekintésben is említettük, az első qubit statisztikái nem változnak (50%-os eséllyel lesz 0 vagy 1), de a második qubit mérésekor __mindig__ ugyanaz az eredmény, mint amit az elsőnél mértünk, mivel a két qubit össze van fonódva!</span><span class="sxs-lookup"><span data-stu-id="0ad52-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ad52-244">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="0ad52-244">Next steps</span></span>

<span data-ttu-id="0ad52-245">A megjelenő "a"-ben a a legelterjedtebb számítási algoritmusok segítségével [megtudhatja](xref:microsoft.quantum.quickstarts.search) , hogyan hozhatja létre és futtathatja a következőt: a a legtöbbet használt, legtöbbet a legtöbbet :::no-loc(Q#)::: kihasználó program, amely a kvantum-számítástechnikai</span><span class="sxs-lookup"><span data-stu-id="0ad52-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a :::no-loc(Q#)::: program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="0ad52-246">[A Quantum Development Kit első lépéseinek](xref:microsoft.quantum.welcome) megismerése és a kvantummechanika további módjai :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="0ad52-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn :::no-loc(Q#)::: and quantum programming.</span></span>
