---
uid: Microsoft.Quantum.Logical.EqualR
title: EQUAL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815977"
---
# <a name="equalr-function"></a><span data-ttu-id="74dc9-102">EQUAL függvény</span><span class="sxs-lookup"><span data-stu-id="74dc9-102">EqualR function</span></span>

<span data-ttu-id="74dc9-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="74dc9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="74dc9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74dc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74dc9-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="74dc9-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="74dc9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="74dc9-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="74dc9-107">a: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="74dc9-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="74dc9-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="74dc9-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="74dc9-109">b: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="74dc9-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="74dc9-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="74dc9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="74dc9-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="74dc9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="74dc9-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="74dc9-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="74dc9-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="74dc9-113">Remarks</span></span>

<span data-ttu-id="74dc9-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="74dc9-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```