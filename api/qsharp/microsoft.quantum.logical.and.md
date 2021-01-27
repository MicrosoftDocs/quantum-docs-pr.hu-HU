---
uid: Microsoft.Quantum.Logical.And
title: És függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849229"
---
# <a name="and-function"></a><span data-ttu-id="93b8d-102">És függvény</span><span class="sxs-lookup"><span data-stu-id="93b8d-102">And function</span></span>

<span data-ttu-id="93b8d-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="93b8d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="93b8d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93b8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93b8d-105">Két érték logikai együttesét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="93b8d-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="93b8d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="93b8d-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="93b8d-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93b8d-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93b8d-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="93b8d-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="93b8d-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93b8d-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93b8d-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="93b8d-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="93b8d-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="93b8d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93b8d-112">`true` Ha és csak akkor, ha `a` és `b` mindkettő `true` .</span><span class="sxs-lookup"><span data-stu-id="93b8d-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93b8d-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="93b8d-113">Remarks</span></span>

<span data-ttu-id="93b8d-114">Az `and` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="93b8d-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="93b8d-115">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="93b8d-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```