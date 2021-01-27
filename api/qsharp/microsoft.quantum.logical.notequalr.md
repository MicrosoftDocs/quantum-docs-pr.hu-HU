---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848504"
---
# <a name="notequalr-function"></a><span data-ttu-id="874da-102">NotEqualR függvény</span><span class="sxs-lookup"><span data-stu-id="874da-102">NotEqualR function</span></span>

<span data-ttu-id="874da-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="874da-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="874da-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="874da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="874da-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="874da-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="874da-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="874da-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="874da-107">a: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="874da-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="874da-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="874da-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="874da-109">b: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="874da-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="874da-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="874da-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="874da-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="874da-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="874da-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="874da-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="874da-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="874da-113">Remarks</span></span>

<span data-ttu-id="874da-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="874da-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```