---
uid: Microsoft.Quantum.Logical.EqualR
title: EQUAL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 5aaa17303d75b27c3ac82cbe7d739a60016fdcb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710029"
---
# <a name="equalr-function"></a><span data-ttu-id="b5b20-102">EQUAL függvény</span><span class="sxs-lookup"><span data-stu-id="b5b20-102">EqualR function</span></span>

<span data-ttu-id="b5b20-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b5b20-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b5b20-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5b20-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5b20-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="b5b20-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="b5b20-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b5b20-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="b5b20-107">a: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="b5b20-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="b5b20-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="b5b20-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="b5b20-109">b: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="b5b20-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="b5b20-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="b5b20-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b5b20-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b5b20-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b5b20-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="b5b20-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5b20-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b5b20-113">Remarks</span></span>

<span data-ttu-id="b5b20-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="b5b20-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualR(a, b);
```