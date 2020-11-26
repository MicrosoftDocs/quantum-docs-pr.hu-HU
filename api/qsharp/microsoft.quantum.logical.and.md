---
uid: Microsoft.Quantum.Logical.And
title: És függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 279221ed785dd76e28146e4c22e70290936bf529
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198571"
---
# <a name="and-function"></a><span data-ttu-id="5177c-102">És függvény</span><span class="sxs-lookup"><span data-stu-id="5177c-102">And function</span></span>

<span data-ttu-id="5177c-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5177c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5177c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5177c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5177c-105">Két érték logikai együttesét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5177c-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5177c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5177c-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5177c-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5177c-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5177c-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="5177c-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5177c-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5177c-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5177c-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="5177c-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5177c-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5177c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5177c-112">`true` Ha és csak akkor, ha `a` és `b` mindkettő `true` .</span><span class="sxs-lookup"><span data-stu-id="5177c-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5177c-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5177c-113">Remarks</span></span>

<span data-ttu-id="5177c-114">Az `and` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="5177c-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="5177c-115">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="5177c-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```