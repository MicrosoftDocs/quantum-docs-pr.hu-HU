---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709454"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="5993b-102">IntsToPaulis függvény</span><span class="sxs-lookup"><span data-stu-id="5993b-102">IntsToPaulis function</span></span>

<span data-ttu-id="5993b-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5993b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5993b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5993b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5993b-105">Egész számok tömbjét alakítja át egy qubit Pauli-operátorok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="5993b-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="5993b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5993b-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="5993b-107">csoportcsomagból: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5993b-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5993b-108">Az egész számokból álló tömb a `0..3`  Pauli-operátorokra konvertálandó tartományban.</span><span class="sxs-lookup"><span data-stu-id="5993b-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="5993b-109">Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="5993b-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="5993b-110">`paulis`A Pauli-operátorok tömbje `Pauli[]` azonos hosszúságú, mint `ints` `paulis[idxPauli]` a megadott elemnek `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="5993b-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>