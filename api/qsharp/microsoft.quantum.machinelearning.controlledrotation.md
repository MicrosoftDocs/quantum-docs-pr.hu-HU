---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847397"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="6ad98-102">ControlledRotation-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="6ad98-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="6ad98-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6ad98-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6ad98-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6ad98-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6ad98-105">Egy vezérelt rotációt mutat be a cél és a vezérlési indexek, a rotációs tengely és az index között a modell paraméterének vektora alapján.</span><span class="sxs-lookup"><span data-stu-id="6ad98-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="6ad98-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="6ad98-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="6ad98-107">TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ad98-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ad98-108">Az ellenőrzött forgatás céljának qubit indexe.</span><span class="sxs-lookup"><span data-stu-id="6ad98-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="6ad98-109">ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6ad98-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6ad98-110">Az adott rotációs vezérlő qubit indexei tömbje.</span><span class="sxs-lookup"><span data-stu-id="6ad98-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="6ad98-111">Tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6ad98-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6ad98-112">A forgatás tengelye</span><span class="sxs-lookup"><span data-stu-id="6ad98-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="6ad98-113">ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ad98-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ad98-114">A modell paraméterének vektoros indexe, amely a forgatás szögét írja le.</span><span class="sxs-lookup"><span data-stu-id="6ad98-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="example"></a><span data-ttu-id="6ad98-115">Példa</span><span class="sxs-lookup"><span data-stu-id="6ad98-115">Example</span></span>

<span data-ttu-id="6ad98-116">Az alábbiakban a regiszter első qubit $X $ tengelyére, a második qubit való vezérlésre, valamint a soros modell negyedik paramétere által megadott szögre vonatkozik:</span><span class="sxs-lookup"><span data-stu-id="6ad98-116">The following represents a rotation about the $X$-axis of the first qubit in a register, controlled on the second qubit, and with an angle given by the fourth parameter in a sequential model:</span></span>

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a><span data-ttu-id="6ad98-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6ad98-117">Remarks</span></span>

<span data-ttu-id="6ad98-118">A nem vezérelt Forgások az `ControlIndices` indexek üres tömbje számára állíthatók be `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="6ad98-118">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>