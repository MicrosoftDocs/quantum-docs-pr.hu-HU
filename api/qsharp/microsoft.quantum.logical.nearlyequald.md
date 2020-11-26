---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197466"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="6da47-102">NearlyEqualD függvény</span><span class="sxs-lookup"><span data-stu-id="6da47-102">NearlyEqualD function</span></span>

<span data-ttu-id="6da47-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6da47-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6da47-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6da47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6da47-105">Igaz értéket ad vissza, ha két bemenet közel egyenlő (azaz a 1e-12 tűréshatáron belül).</span><span class="sxs-lookup"><span data-stu-id="6da47-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6da47-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6da47-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6da47-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6da47-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6da47-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="6da47-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6da47-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6da47-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6da47-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="6da47-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6da47-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6da47-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6da47-112">`true` Ha és csak akkor, ha `a` majdnem egyenlő a következővel: `b` .</span><span class="sxs-lookup"><span data-stu-id="6da47-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6da47-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6da47-113">Remarks</span></span>

<span data-ttu-id="6da47-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="6da47-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```