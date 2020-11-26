---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: fe2babb87d716185286b0864745f7ff6e637f8a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207010"
---
# <a name="delayedca-function"></a><span data-ttu-id="19993-102">DelayedCA függvény</span><span class="sxs-lookup"><span data-stu-id="19993-102">DelayedCA function</span></span>

<span data-ttu-id="19993-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="19993-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="19993-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19993-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19993-105">Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="19993-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="19993-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="19993-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="19993-107">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="19993-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="19993-108">A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="19993-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="19993-109">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="19993-109">arg : 'T</span></span>

<span data-ttu-id="19993-110">Az a bemenet, amelyre a művelet `op` vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="19993-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="19993-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="19993-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="19993-112">Egy új művelet, amely `op` a bemenetre vonatkozik `arg`</span><span class="sxs-lookup"><span data-stu-id="19993-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="19993-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="19993-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="19993-114">Nem</span><span class="sxs-lookup"><span data-stu-id="19993-114">'T</span></span>

<span data-ttu-id="19993-115">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="19993-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="19993-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="19993-116">See Also</span></span>

- [<span data-ttu-id="19993-117">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="19993-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="19993-118">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="19993-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)