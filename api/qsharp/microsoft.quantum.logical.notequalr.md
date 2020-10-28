---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709791"
---
# <a name="notequalr-function"></a><span data-ttu-id="b555e-102">NotEqualR függvény</span><span class="sxs-lookup"><span data-stu-id="b555e-102">NotEqualR function</span></span>

<span data-ttu-id="b555e-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b555e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b555e-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b555e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b555e-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="b555e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="b555e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b555e-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="b555e-107">a: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="b555e-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="b555e-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="b555e-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="b555e-109">b: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="b555e-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="b555e-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="b555e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b555e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b555e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b555e-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="b555e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b555e-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b555e-113">Remarks</span></span>

<span data-ttu-id="b555e-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="b555e-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```