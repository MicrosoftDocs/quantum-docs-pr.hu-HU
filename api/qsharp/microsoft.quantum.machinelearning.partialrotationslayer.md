---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ade0640b07f633982e98d5d02239fa205909bcce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196242"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="b9c68-102">PartialRotationsLayer függvény</span><span class="sxs-lookup"><span data-stu-id="b9c68-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="b9c68-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b9c68-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b9c68-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b9c68-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b9c68-105">Egy qubit-forgás tömbjét adja vissza egy adott tengelyen, a paramétert pedig a különböző modell paraméterekkel együtt.</span><span class="sxs-lookup"><span data-stu-id="b9c68-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="b9c68-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b9c68-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="b9c68-107">idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b9c68-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b9c68-108">A qubits az egyes rotációs célokhoz használandó indexek.</span><span class="sxs-lookup"><span data-stu-id="b9c68-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="b9c68-109">tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b9c68-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b9c68-110">Az adott réteg minden egyes forgásának rotációs tengelye</span><span class="sxs-lookup"><span data-stu-id="b9c68-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="b9c68-111">Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="b9c68-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="b9c68-112">A megadott tengelyre vonatkozó vezérelt rotációs tömb, amely az egyes `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="b9c68-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>