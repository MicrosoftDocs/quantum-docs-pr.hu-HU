---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198027"
---
# <a name="greaterthand-function"></a><span data-ttu-id="e1453-102">GreaterThanD függvény</span><span class="sxs-lookup"><span data-stu-id="e1453-102">GreaterThanD function</span></span>

<span data-ttu-id="e1453-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e1453-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e1453-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1453-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1453-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="e1453-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e1453-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e1453-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e1453-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e1453-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e1453-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="e1453-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e1453-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e1453-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e1453-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="e1453-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e1453-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e1453-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e1453-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="e1453-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1453-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e1453-113">Remarks</span></span>

<span data-ttu-id="e1453-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="e1453-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```