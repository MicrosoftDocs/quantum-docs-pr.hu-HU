---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720725"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="1533b-102">NotNearlyEqualD függvény</span><span class="sxs-lookup"><span data-stu-id="1533b-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="1533b-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1533b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1533b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1533b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1533b-105">Igaz értéket ad vissza, ha két bemenet közel nem egyenlő (azaz nem a 1e-12 tűréshatáron belül van).</span><span class="sxs-lookup"><span data-stu-id="1533b-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="1533b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1533b-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="1533b-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1533b-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1533b-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="1533b-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="1533b-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1533b-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1533b-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="1533b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1533b-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1533b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1533b-112">`true` Ha és csak akkor, ha `a` majdnem nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="1533b-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1533b-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1533b-113">Remarks</span></span>

<span data-ttu-id="1533b-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="1533b-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```