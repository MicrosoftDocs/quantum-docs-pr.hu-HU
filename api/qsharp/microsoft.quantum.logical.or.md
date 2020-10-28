---
uid: Microsoft.Quantum.Logical.Or
title: Vagy függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719980"
---
# <a name="or-function"></a><span data-ttu-id="ab2d0-102">Vagy függvény</span><span class="sxs-lookup"><span data-stu-id="ab2d0-102">Or function</span></span>

<span data-ttu-id="ab2d0-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ab2d0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ab2d0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab2d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab2d0-105">Két érték logikai kiválasztását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ab2d0-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="ab2d0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ab2d0-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="ab2d0-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ab2d0-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ab2d0-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="ab2d0-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="ab2d0-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ab2d0-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ab2d0-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="ab2d0-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ab2d0-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ab2d0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ab2d0-112">`true` Ha és csak akkor, ha `a` vagy `b` a vagy a `true` .</span><span class="sxs-lookup"><span data-stu-id="ab2d0-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab2d0-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ab2d0-113">Remarks</span></span>

<span data-ttu-id="ab2d0-114">Az `or` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="ab2d0-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="ab2d0-115">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="ab2d0-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```