---
uid: Microsoft.Quantum.Logical.Conditioned
title: Feltételes függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720785"
---
# <a name="conditioned-function"></a><span data-ttu-id="cfef5-102">Feltételes függvény</span><span class="sxs-lookup"><span data-stu-id="cfef5-102">Conditioned function</span></span>

<span data-ttu-id="cfef5-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cfef5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cfef5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cfef5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cfef5-105">Egy logikai feltétel értékétől függően két érték egyikét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="cfef5-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="cfef5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cfef5-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="cfef5-107">feltétel: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cfef5-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cfef5-108">A visszaadott bemenet szabályozására szolgáló feltétel.</span><span class="sxs-lookup"><span data-stu-id="cfef5-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="cfef5-109">ifTrue: nem</span><span class="sxs-lookup"><span data-stu-id="cfef5-109">ifTrue : 'T</span></span>

<span data-ttu-id="cfef5-110">Az értékeként visszaadott érték `condition` `true` .</span><span class="sxs-lookup"><span data-stu-id="cfef5-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="cfef5-111">ifFalse: nem</span><span class="sxs-lookup"><span data-stu-id="cfef5-111">ifFalse : 'T</span></span>

<span data-ttu-id="cfef5-112">Az értékeként visszaadott érték `condition` `false` .</span><span class="sxs-lookup"><span data-stu-id="cfef5-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="cfef5-113">Kimenet: nem</span><span class="sxs-lookup"><span data-stu-id="cfef5-113">Output : 'T</span></span>

<span data-ttu-id="cfef5-114">`ifTrue` Ha `condition` van `true` , és `ifFalse` egyéb módon.</span><span class="sxs-lookup"><span data-stu-id="cfef5-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cfef5-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="cfef5-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cfef5-116">Nem</span><span class="sxs-lookup"><span data-stu-id="cfef5-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="cfef5-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cfef5-117">Remarks</span></span>

<span data-ttu-id="cfef5-118">Az `?|` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="cfef5-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="cfef5-119">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="cfef5-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```