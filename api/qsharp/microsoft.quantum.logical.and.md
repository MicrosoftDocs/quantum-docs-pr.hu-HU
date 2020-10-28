---
uid: Microsoft.Quantum.Logical.And
title: És függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720797"
---
# <a name="and-function"></a><span data-ttu-id="62b9c-102">És függvény</span><span class="sxs-lookup"><span data-stu-id="62b9c-102">And function</span></span>

<span data-ttu-id="62b9c-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="62b9c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="62b9c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62b9c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62b9c-105">Két érték logikai együttesét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="62b9c-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="62b9c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="62b9c-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="62b9c-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="62b9c-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="62b9c-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="62b9c-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="62b9c-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="62b9c-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="62b9c-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="62b9c-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="62b9c-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="62b9c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="62b9c-112">`true` Ha és csak akkor, ha `a` és `b` mindkettő `true` .</span><span class="sxs-lookup"><span data-stu-id="62b9c-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="62b9c-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="62b9c-113">Remarks</span></span>

<span data-ttu-id="62b9c-114">Az `and` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="62b9c-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="62b9c-115">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="62b9c-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```