---
uid: Microsoft.Quantum.Logical.Or
title: Vagy függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848464"
---
# <a name="or-function"></a><span data-ttu-id="c00e1-102">Vagy függvény</span><span class="sxs-lookup"><span data-stu-id="c00e1-102">Or function</span></span>

<span data-ttu-id="c00e1-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c00e1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c00e1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c00e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c00e1-105">Két érték logikai kiválasztását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c00e1-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="c00e1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c00e1-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="c00e1-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c00e1-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c00e1-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="c00e1-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="c00e1-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c00e1-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c00e1-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="c00e1-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c00e1-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c00e1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c00e1-112">`true` Ha és csak akkor, ha `a` vagy `b` a vagy a `true` .</span><span class="sxs-lookup"><span data-stu-id="c00e1-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c00e1-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c00e1-113">Remarks</span></span>

<span data-ttu-id="c00e1-114">Az `or` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="c00e1-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="c00e1-115">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="c00e1-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```