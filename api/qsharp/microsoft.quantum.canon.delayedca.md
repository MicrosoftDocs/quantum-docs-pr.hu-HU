---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716217"
---
# <a name="delayedca-function"></a><span data-ttu-id="033cb-102">DelayedCA függvény</span><span class="sxs-lookup"><span data-stu-id="033cb-102">DelayedCA function</span></span>

<span data-ttu-id="033cb-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="033cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="033cb-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="033cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="033cb-105">Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="033cb-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="033cb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="033cb-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="033cb-107">op: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="033cb-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="033cb-108">A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="033cb-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="033cb-109">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="033cb-109">arg : 'T</span></span>

<span data-ttu-id="033cb-110">Az a bemenet, amelyre a művelet `op` vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="033cb-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="033cb-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="033cb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="033cb-112">Egy új művelet, amely `op` a bemenetre vonatkozik `arg`</span><span class="sxs-lookup"><span data-stu-id="033cb-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="033cb-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="033cb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="033cb-114">Nem</span><span class="sxs-lookup"><span data-stu-id="033cb-114">'T</span></span>

<span data-ttu-id="033cb-115">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="033cb-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="033cb-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="033cb-116">See Also</span></span>

- [<span data-ttu-id="033cb-117">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="033cb-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="033cb-118">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="033cb-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)