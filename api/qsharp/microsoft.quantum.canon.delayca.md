---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4b4be55436d6619511a12c6fb7fbd0f23989152a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716272"
---
# <a name="delayca-operation"></a><span data-ttu-id="eeb7c-102">DelayCA művelet</span><span class="sxs-lookup"><span data-stu-id="eeb7c-102">DelayCA operation</span></span>

<span data-ttu-id="eeb7c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eeb7c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eeb7c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eeb7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eeb7c-105">Egy megadott műveletet késleltetve alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="eeb7c-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="eeb7c-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="eeb7c-106">Description</span></span>

<span data-ttu-id="eeb7c-107">Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="eeb7c-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="eeb7c-108">A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="eeb7c-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="eeb7c-109">`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .</span><span class="sxs-lookup"><span data-stu-id="eeb7c-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="eeb7c-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eeb7c-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="eeb7c-111">op: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="eeb7c-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="eeb7c-112">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="eeb7c-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="eeb7c-113">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="eeb7c-113">arg : 'T</span></span>

<span data-ttu-id="eeb7c-114">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="eeb7c-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="eeb7c-115">AUX: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eeb7c-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="eeb7c-116">A művelet alkalmazásának a részleges alkalmazás használatával történő késleltetésére szolgáló argumentum.</span><span class="sxs-lookup"><span data-stu-id="eeb7c-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eeb7c-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eeb7c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eeb7c-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="eeb7c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eeb7c-119">Nem</span><span class="sxs-lookup"><span data-stu-id="eeb7c-119">'T</span></span>

<span data-ttu-id="eeb7c-120">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="eeb7c-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="eeb7c-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="eeb7c-121">See Also</span></span>

- [<span data-ttu-id="eeb7c-122">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="eeb7c-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="eeb7c-123">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="eeb7c-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)