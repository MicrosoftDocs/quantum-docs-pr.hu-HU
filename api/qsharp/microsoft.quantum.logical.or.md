---
uid: Microsoft.Quantum.Logical.Or
title: Vagy függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 7093d908696a8cfda6b5ef648f9dfafcfac97144
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197126"
---
# <a name="or-function"></a><span data-ttu-id="52171-102">Vagy függvény</span><span class="sxs-lookup"><span data-stu-id="52171-102">Or function</span></span>

<span data-ttu-id="52171-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="52171-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="52171-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52171-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52171-105">Két érték logikai kiválasztását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="52171-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="52171-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="52171-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="52171-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="52171-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="52171-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="52171-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="52171-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="52171-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="52171-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="52171-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="52171-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="52171-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="52171-112">`true` Ha és csak akkor, ha `a` vagy `b` a vagy a `true` .</span><span class="sxs-lookup"><span data-stu-id="52171-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="52171-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="52171-113">Remarks</span></span>

<span data-ttu-id="52171-114">Az `or` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="52171-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="52171-115">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="52171-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```