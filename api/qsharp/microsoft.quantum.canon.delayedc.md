---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207011"
---
# <a name="delayedc-function"></a><span data-ttu-id="39091-102">DelayedC függvény</span><span class="sxs-lookup"><span data-stu-id="39091-102">DelayedC function</span></span>

<span data-ttu-id="39091-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39091-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39091-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39091-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39091-105">Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="39091-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="39091-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="39091-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="39091-107">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="39091-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="39091-108">A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="39091-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="39091-109">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="39091-109">arg : 'T</span></span>

<span data-ttu-id="39091-110">Az a bemenet, amelyre a művelet `op` vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="39091-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="39091-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="39091-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="39091-112">Egy új művelet, amely `op` a bemenetre vonatkozik `arg`</span><span class="sxs-lookup"><span data-stu-id="39091-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39091-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="39091-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39091-114">Nem</span><span class="sxs-lookup"><span data-stu-id="39091-114">'T</span></span>

<span data-ttu-id="39091-115">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="39091-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="39091-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="39091-116">See Also</span></span>

- [<span data-ttu-id="39091-117">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="39091-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="39091-118">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="39091-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)