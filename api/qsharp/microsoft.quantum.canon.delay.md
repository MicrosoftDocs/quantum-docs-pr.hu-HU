---
uid: Microsoft.Quantum.Canon.Delay
title: Késleltetési művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716315"
---
# <a name="delay-operation"></a><span data-ttu-id="7cdaf-102">Késleltetési művelet</span><span class="sxs-lookup"><span data-stu-id="7cdaf-102">Delay operation</span></span>

<span data-ttu-id="7cdaf-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7cdaf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7cdaf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7cdaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7cdaf-105">Egy megadott műveletet késleltetve alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="7cdaf-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="7cdaf-106">Description</span></span>

<span data-ttu-id="7cdaf-107">Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="7cdaf-108">A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="7cdaf-109">`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .</span><span class="sxs-lookup"><span data-stu-id="7cdaf-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="7cdaf-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7cdaf-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="7cdaf-111">op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="7cdaf-111">op : 'T => 'U</span></span> 

<span data-ttu-id="7cdaf-112">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="7cdaf-113">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="7cdaf-113">arg : 'T</span></span>

<span data-ttu-id="7cdaf-114">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="7cdaf-115">AUX: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7cdaf-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="7cdaf-116">A művelet alkalmazásának a részleges alkalmazás használatával történő késleltetésére szolgáló argumentum.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="7cdaf-117">Kimenet: U</span><span class="sxs-lookup"><span data-stu-id="7cdaf-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7cdaf-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7cdaf-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7cdaf-119">Nem</span><span class="sxs-lookup"><span data-stu-id="7cdaf-119">'T</span></span>

<span data-ttu-id="7cdaf-120">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="7cdaf-121">' U</span><span class="sxs-lookup"><span data-stu-id="7cdaf-121">'U</span></span>

<span data-ttu-id="7cdaf-122">A késleltetni kívánt művelet visszatérési típusa.</span><span class="sxs-lookup"><span data-stu-id="7cdaf-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cdaf-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7cdaf-123">See Also</span></span>

- [<span data-ttu-id="7cdaf-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="7cdaf-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="7cdaf-125">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="7cdaf-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="7cdaf-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="7cdaf-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="7cdaf-127">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="7cdaf-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)