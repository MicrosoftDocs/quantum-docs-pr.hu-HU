---
title: 'Q # introdution'
description: 'Gyors bevezetés a Quantum programba a Q-ban #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233979"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="8318e-103">Q # Quantum programozási nyelv</span><span class="sxs-lookup"><span data-stu-id="8318e-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="8318e-104">Minden, amit tudnia kell a Q # programozási nyelvről, részletesen szerepel a [q # nyelvi útmutatójában](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="8318e-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="8318e-105">Mint bármi más, a [nyelvi tervezési folyamat](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) nyílt forráskódú, és szívesen vesszük a hozzájárulásokat.</span><span class="sxs-lookup"><span data-stu-id="8318e-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="8318e-106">Ha többet szeretne megtudni az alapjairól és a Q # mögötti motivációról, olvassa el a [Miért van szükségünk q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)című témakört.</span><span class="sxs-lookup"><span data-stu-id="8318e-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="8318e-107">A Q # a Quantum Development Kit (QDK) részeként érhető el egy gyors áttekintéshez, és nézze meg, [Mi a QDK?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="8318e-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="8318e-108">Mi az a Quantum program?</span><span class="sxs-lookup"><span data-stu-id="8318e-108">What is a quantum program?</span></span>

<span data-ttu-id="8318e-109">A kvantum-programok a klasszikus alrutinok egy adott készletének tekinthetők meg, amelyek hívásakor a rendszer egy kvantum-rendszerrel való interakcióval végez számítást. a Q #-ban írt programok nem modellezik közvetlenül a kvantum-állapotot, hanem azt, hogy egy klasszikus vezérlő számítógép hogyan kommunikál a qubits.</span><span class="sxs-lookup"><span data-stu-id="8318e-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="8318e-110">Ez lehetővé teszi számunkra, hogy teljesen függetlenek legyenek attól, hogy milyen kvantum-állapotot biztosítanak *az egyes* célszámítógépeken, ami különböző értelmezésekkel rendelkezhet a gépen.</span><span class="sxs-lookup"><span data-stu-id="8318e-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="8318e-111">Ennek egyik fontos következménye, hogy a Q # nem tud betekintést adni egy qubit vagy más, a kvantummechanika állapotára, ami garantálja, hogy a Q # program fizikailag végrehajtható a kvantum-számítógépeken.</span><span class="sxs-lookup"><span data-stu-id="8318e-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="8318e-112">Ehelyett egy program olyan műveleteket hívhat meg, mint például [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) a klasszikus információk qubit való kinyerése.</span><span class="sxs-lookup"><span data-stu-id="8318e-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="8318e-113">A foglalást követően a qubit a műveleteknek és a függvényeknek, más néven *callables* is átadható.</span><span class="sxs-lookup"><span data-stu-id="8318e-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="8318e-114">Bizonyos értelemben ez azt eredményezi, hogy a Q # program egy qubit tud tenni; A qubit állapotával kapcsolatos közvetlen műveleteket az összes *belső* callables, például [`X`](xref:Microsoft.Quantum.Intrinsic.X) a és-, [`H`](xref:Microsoft.Quantum.Intrinsic.H) azaz a callables határozzák meg, amelyek implementációi nem a Q #-ban vannak definiálva, hanem a célszámítógép által definiált módon.</span><span class="sxs-lookup"><span data-stu-id="8318e-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="8318e-115">Ezeket a műveleteket ténylegesen csak az adott Q # program futtatásához használt célszámítógép *végzi el.*</span><span class="sxs-lookup"><span data-stu-id="8318e-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="8318e-116">Ha például a programot a [teljes állapotú szimulátoron](xref:microsoft.quantum.machines.full-state-simulator)futtatja, a szimulátor a szimulált kvantum-rendszernek megfelelő matematikai műveleteket hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="8318e-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="8318e-117">De a jövő irányába szemlélve, amikor a célszámítógép egy valódi kvantum-számítógép, a Q #-ban az ilyen műveletek meghívásával irányítja a kvantum-számítógépet, hogy végrehajtsa a megfelelő *valós* műveleteket a *valós* kvantum-rendszeren (például a pontosan időzített lézeres impulzusok esetében).</span><span class="sxs-lookup"><span data-stu-id="8318e-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="8318e-118">A Q # program újrakombinálja ezeket a műveleteket a célszámítógép által meghatározott módon, hogy új, magasabb szintű műveleteket hozzon létre a kvantum-számításokhoz.</span><span class="sxs-lookup"><span data-stu-id="8318e-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="8318e-119">Így a Q # megkönnyíti a Quantum és a hibrid kvantum – klasszikus algoritmusok kiépítését, és egyúttal általános megoldást is biztosít a célszámítógép vagy a szimulátor struktúrájára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="8318e-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="8318e-120">Egy egyszerű példa a következő program, amely egy qubit foglal le a $ \ket {0} $ állapotban, majd Hadamard műveletet alkalmaz `H` rá, és az eredményt az `PauliZ` alapján méri.</span><span class="sxs-lookup"><span data-stu-id="8318e-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="8318e-121">A [Quantum katas](https://github.com/microsoft/QuantumKatas#introduction) kiváló bevezetést biztosít a [kvantum-számítástechnikai fogalmakkal](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , például a közös kvantum-műveletekkel és a qubits kezelésével kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="8318e-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="8318e-122">További példákat is találhat a [belső műveletekben és a függvényekben](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="8318e-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



