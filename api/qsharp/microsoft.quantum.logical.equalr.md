---
uid: Microsoft.Quantum.Logical.EqualR
title: EQUAL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d68b2f1a26bf318400d3c88b37d9aabcc38cbdfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198006"
---
# <a name="equalr-function"></a><span data-ttu-id="df97b-102">EQUAL függvény</span><span class="sxs-lookup"><span data-stu-id="df97b-102">EqualR function</span></span>

<span data-ttu-id="df97b-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="df97b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="df97b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df97b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df97b-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="df97b-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="df97b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df97b-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="df97b-107">a: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="df97b-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="df97b-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="df97b-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="df97b-109">b: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="df97b-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="df97b-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="df97b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="df97b-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df97b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df97b-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="df97b-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="df97b-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="df97b-113">Remarks</span></span>

<span data-ttu-id="df97b-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="df97b-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```