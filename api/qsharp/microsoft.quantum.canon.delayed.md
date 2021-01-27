---
uid: Microsoft.Quantum.Canon.Delayed
title: Késleltetett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840588"
---
# <a name="delayed-function"></a><span data-ttu-id="8921f-102">Késleltetett függvény</span><span class="sxs-lookup"><span data-stu-id="8921f-102">Delayed function</span></span>

<span data-ttu-id="8921f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8921f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8921f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8921f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8921f-105">Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="8921f-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="8921f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8921f-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="8921f-107">op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="8921f-107">op : 'T => 'U</span></span> 

<span data-ttu-id="8921f-108">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="8921f-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="8921f-109">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="8921f-109">arg : 'T</span></span>

<span data-ttu-id="8921f-110">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="8921f-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="8921f-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => U</span><span class="sxs-lookup"><span data-stu-id="8921f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="8921f-112">Egy új művelet, amely `op` a bemenetre vonatkozik `arg`</span><span class="sxs-lookup"><span data-stu-id="8921f-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8921f-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8921f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8921f-114">Nem</span><span class="sxs-lookup"><span data-stu-id="8921f-114">'T</span></span>

<span data-ttu-id="8921f-115">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="8921f-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="8921f-116">' U</span><span class="sxs-lookup"><span data-stu-id="8921f-116">'U</span></span>

<span data-ttu-id="8921f-117">A késleltetni kívánt művelet visszatérési típusa.</span><span class="sxs-lookup"><span data-stu-id="8921f-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="8921f-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8921f-118">See Also</span></span>

- [<span data-ttu-id="8921f-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="8921f-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="8921f-120">Microsoft. Quantum. Canon. késleltetett</span><span class="sxs-lookup"><span data-stu-id="8921f-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="8921f-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="8921f-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="8921f-122">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="8921f-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)