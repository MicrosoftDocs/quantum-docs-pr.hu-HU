---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720509"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="b8bee-102">CyclicEntanglingLayer függvény</span><span class="sxs-lookup"><span data-stu-id="b8bee-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="b8bee-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b8bee-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b8bee-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8bee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8bee-105">Egy, az adott tengelyen lévő, jól vezérelt rotációs tömböt ad vissza, amelyet ciklikusan rendeznek a qubits-jegyzékben, és különböző modell-paraméterekkel rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="b8bee-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="b8bee-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b8bee-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b8bee-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8bee-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8bee-108">Az adott réteg által lejátszott qubits száma.</span><span class="sxs-lookup"><span data-stu-id="b8bee-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="b8bee-109">tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b8bee-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b8bee-110">Az adott réteg minden egyes forgásának rotációs tengelye</span><span class="sxs-lookup"><span data-stu-id="b8bee-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="b8bee-111">lépéshossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8bee-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8bee-112">A cél és a vezérlő indexek közötti elkülönítés az egyes rotációk esetében.</span><span class="sxs-lookup"><span data-stu-id="b8bee-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="b8bee-113">Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="b8bee-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="b8bee-114">A kétqubitos vezérelt rotációk tömbje ciklikusan, a qubits-jegyzéken belül van meghatározva `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="b8bee-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>