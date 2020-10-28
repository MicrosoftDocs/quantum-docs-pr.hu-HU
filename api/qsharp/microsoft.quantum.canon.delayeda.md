---
uid: Microsoft.Quantum.Canon.DelayedA
title: Késleltetett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716245"
---
# <a name="delayeda-function"></a><span data-ttu-id="73e95-102">Késleltetett függvény</span><span class="sxs-lookup"><span data-stu-id="73e95-102">DelayedA function</span></span>

<span data-ttu-id="73e95-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73e95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73e95-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="73e95-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="73e95-105">Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="73e95-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="73e95-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="73e95-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="73e95-107">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="73e95-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="73e95-108">A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="73e95-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="73e95-109">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="73e95-109">arg : 'T</span></span>

<span data-ttu-id="73e95-110">Az a bemenet, amelyre a művelet `op` vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="73e95-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="73e95-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit) – helyesbítés</span><span class="sxs-lookup"><span data-stu-id="73e95-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="73e95-112">Egy új művelet, amely `op` a bemenetre vonatkozik `arg`</span><span class="sxs-lookup"><span data-stu-id="73e95-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="73e95-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="73e95-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="73e95-114">Nem</span><span class="sxs-lookup"><span data-stu-id="73e95-114">'T</span></span>

<span data-ttu-id="73e95-115">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="73e95-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="73e95-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="73e95-116">See Also</span></span>

- [<span data-ttu-id="73e95-117">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="73e95-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="73e95-118">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="73e95-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)