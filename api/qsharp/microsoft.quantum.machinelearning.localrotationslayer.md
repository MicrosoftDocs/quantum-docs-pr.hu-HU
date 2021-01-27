---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: a3658bbf62068c9eea2d9b763cbff5596f426135
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854981"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="cc4ed-102">LocalRotationsLayer függvény</span><span class="sxs-lookup"><span data-stu-id="cc4ed-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="cc4ed-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="cc4ed-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="cc4ed-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="cc4ed-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="cc4ed-105">Egy olyan tömböt ad vissza, amely egy adott tengelyen nem vezérelt (Single-qubit) rotációt eredményez, és a regiszterben lévő minden egyes qubit egy rotációs paraméterrel van ellátva.</span><span class="sxs-lookup"><span data-stu-id="cc4ed-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="cc4ed-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cc4ed-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="cc4ed-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cc4ed-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cc4ed-108">Az adott réteg által lejátszott qubits száma.</span><span class="sxs-lookup"><span data-stu-id="cc4ed-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="cc4ed-109">tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="cc4ed-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="cc4ed-110">Az adott réteg minden egyes forgásának rotációs tengelye</span><span class="sxs-lookup"><span data-stu-id="cc4ed-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="cc4ed-111">Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="cc4ed-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="cc4ed-112">A megadott tengelyre vonatkozó vezérelt rotációs tömb, amely az egyes `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="cc4ed-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>