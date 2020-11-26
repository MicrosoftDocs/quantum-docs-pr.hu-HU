---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197194"
---
# <a name="notequalr-function"></a><span data-ttu-id="d99c4-102">NotEqualR függvény</span><span class="sxs-lookup"><span data-stu-id="d99c4-102">NotEqualR function</span></span>

<span data-ttu-id="d99c4-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d99c4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d99c4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d99c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d99c4-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="d99c4-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="d99c4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d99c4-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="d99c4-107">a: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="d99c4-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="d99c4-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="d99c4-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="d99c4-109">b: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="d99c4-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="d99c4-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="d99c4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d99c4-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d99c4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d99c4-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="d99c4-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d99c4-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d99c4-113">Remarks</span></span>

<span data-ttu-id="d99c4-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="d99c4-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```