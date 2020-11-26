---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: LocalRotationsLayer függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 1549f24427f19bacbadf72e00c1c0181b64bcb73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211729"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="519e1-102">LocalRotationsLayer függvény</span><span class="sxs-lookup"><span data-stu-id="519e1-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="519e1-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="519e1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="519e1-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="519e1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="519e1-105">Egy olyan tömböt ad vissza, amely egy adott tengelyen nem vezérelt (Single-qubit) rotációt eredményez, és a regiszterben lévő minden egyes qubit egy rotációs paraméterrel van ellátva.</span><span class="sxs-lookup"><span data-stu-id="519e1-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="519e1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="519e1-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="519e1-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="519e1-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="519e1-108">Az adott réteg által lejátszott qubits száma.</span><span class="sxs-lookup"><span data-stu-id="519e1-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="519e1-109">tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="519e1-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="519e1-110">Az adott réteg minden egyes forgásának rotációs tengelye</span><span class="sxs-lookup"><span data-stu-id="519e1-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="519e1-111">Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="519e1-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="519e1-112">A megadott tengelyre vonatkozó vezérelt rotációs tömb, amely az egyes `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="519e1-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>