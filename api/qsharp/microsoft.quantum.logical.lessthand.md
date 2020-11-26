---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197738"
---
# <a name="lessthand-function"></a><span data-ttu-id="26b47-102">LessThanD függvény</span><span class="sxs-lookup"><span data-stu-id="26b47-102">LessThanD function</span></span>

<span data-ttu-id="26b47-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="26b47-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="26b47-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26b47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26b47-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="26b47-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="26b47-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="26b47-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="26b47-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="26b47-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="26b47-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="26b47-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="26b47-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="26b47-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="26b47-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="26b47-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="26b47-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26b47-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26b47-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan kisebb `b` .</span><span class="sxs-lookup"><span data-stu-id="26b47-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26b47-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="26b47-113">Remarks</span></span>

<span data-ttu-id="26b47-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="26b47-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```