---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 91ab51180018a9b95a2f9010477c0a24f3a54617
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720784"
---
# <a name="equalb-function"></a><span data-ttu-id="a46de-102">EqualB függvény</span><span class="sxs-lookup"><span data-stu-id="a46de-102">EqualB function</span></span>

<span data-ttu-id="a46de-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a46de-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a46de-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a46de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a46de-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="a46de-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="a46de-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a46de-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="a46de-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a46de-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a46de-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="a46de-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="a46de-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a46de-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a46de-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="a46de-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a46de-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a46de-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a46de-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="a46de-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a46de-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a46de-113">Remarks</span></span>

<span data-ttu-id="a46de-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="a46de-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualB(a, b);
```