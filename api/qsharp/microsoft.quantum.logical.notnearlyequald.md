---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848485"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="57daf-102">NotNearlyEqualD függvény</span><span class="sxs-lookup"><span data-stu-id="57daf-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="57daf-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="57daf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="57daf-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57daf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57daf-105">Igaz értéket ad vissza, ha két bemenet közel nem egyenlő (azaz nem a 1e-12 tűréshatáron belül van).</span><span class="sxs-lookup"><span data-stu-id="57daf-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="57daf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="57daf-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="57daf-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="57daf-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="57daf-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="57daf-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="57daf-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="57daf-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="57daf-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="57daf-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="57daf-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="57daf-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="57daf-112">`true` Ha és csak akkor, ha `a` majdnem nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="57daf-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="57daf-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="57daf-113">Remarks</span></span>

<span data-ttu-id="57daf-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="57daf-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```