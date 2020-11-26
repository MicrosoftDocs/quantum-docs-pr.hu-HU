---
uid: Microsoft.Quantum.Logical.Conditioned
title: Feltételes függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198486"
---
# <a name="conditioned-function"></a><span data-ttu-id="fc7ec-102">Feltételes függvény</span><span class="sxs-lookup"><span data-stu-id="fc7ec-102">Conditioned function</span></span>

<span data-ttu-id="fc7ec-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fc7ec-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fc7ec-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc7ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc7ec-105">Egy logikai feltétel értékétől függően két érték egyikét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fc7ec-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="fc7ec-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fc7ec-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="fc7ec-107">feltétel: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fc7ec-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fc7ec-108">A visszaadott bemenet szabályozására szolgáló feltétel.</span><span class="sxs-lookup"><span data-stu-id="fc7ec-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="fc7ec-109">ifTrue: nem</span><span class="sxs-lookup"><span data-stu-id="fc7ec-109">ifTrue : 'T</span></span>

<span data-ttu-id="fc7ec-110">Az értékeként visszaadott érték `condition` `true` .</span><span class="sxs-lookup"><span data-stu-id="fc7ec-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="fc7ec-111">ifFalse: nem</span><span class="sxs-lookup"><span data-stu-id="fc7ec-111">ifFalse : 'T</span></span>

<span data-ttu-id="fc7ec-112">Az értékeként visszaadott érték `condition` `false` .</span><span class="sxs-lookup"><span data-stu-id="fc7ec-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="fc7ec-113">Kimenet: nem</span><span class="sxs-lookup"><span data-stu-id="fc7ec-113">Output : 'T</span></span>

<span data-ttu-id="fc7ec-114">`ifTrue` Ha `condition` van `true` , és `ifFalse` egyéb módon.</span><span class="sxs-lookup"><span data-stu-id="fc7ec-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fc7ec-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="fc7ec-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc7ec-116">Nem</span><span class="sxs-lookup"><span data-stu-id="fc7ec-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="fc7ec-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fc7ec-117">Remarks</span></span>

<span data-ttu-id="fc7ec-118">Az `?|` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.</span><span class="sxs-lookup"><span data-stu-id="fc7ec-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="fc7ec-119">Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="fc7ec-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```