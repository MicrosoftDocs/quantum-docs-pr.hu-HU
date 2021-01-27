---
uid: Microsoft.Quantum.Canon.Delay
title: Késleltetési művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840655"
---
# <a name="delay-operation"></a><span data-ttu-id="152f8-102">Késleltetési művelet</span><span class="sxs-lookup"><span data-stu-id="152f8-102">Delay operation</span></span>

<span data-ttu-id="152f8-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="152f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="152f8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="152f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="152f8-105">Egy megadott műveletet késleltetve alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="152f8-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="152f8-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="152f8-106">Description</span></span>

<span data-ttu-id="152f8-107">Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="152f8-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="152f8-108">A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="152f8-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="152f8-109">`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .</span><span class="sxs-lookup"><span data-stu-id="152f8-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="152f8-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="152f8-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="152f8-111">op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="152f8-111">op : 'T => 'U</span></span> 

<span data-ttu-id="152f8-112">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="152f8-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="152f8-113">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="152f8-113">arg : 'T</span></span>

<span data-ttu-id="152f8-114">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="152f8-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="152f8-115">AUX: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="152f8-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="152f8-116">A művelet alkalmazásának a részleges alkalmazás használatával történő késleltetésére szolgáló argumentum.</span><span class="sxs-lookup"><span data-stu-id="152f8-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="152f8-117">Kimenet: U</span><span class="sxs-lookup"><span data-stu-id="152f8-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="152f8-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="152f8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="152f8-119">Nem</span><span class="sxs-lookup"><span data-stu-id="152f8-119">'T</span></span>

<span data-ttu-id="152f8-120">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="152f8-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="152f8-121">' U</span><span class="sxs-lookup"><span data-stu-id="152f8-121">'U</span></span>

<span data-ttu-id="152f8-122">A késleltetni kívánt művelet visszatérési típusa.</span><span class="sxs-lookup"><span data-stu-id="152f8-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="152f8-123">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="152f8-123">See Also</span></span>

- [<span data-ttu-id="152f8-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="152f8-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="152f8-125">Microsoft. Quantum. Canon. Delaya</span><span class="sxs-lookup"><span data-stu-id="152f8-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="152f8-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="152f8-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="152f8-127">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="152f8-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)