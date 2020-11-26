---
uid: Microsoft.Quantum.Canon.DelayA
title: Késleltetési művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207139"
---
# <a name="delaya-operation"></a><span data-ttu-id="b2a5d-102">Késleltetési művelet</span><span class="sxs-lookup"><span data-stu-id="b2a5d-102">DelayA operation</span></span>

<span data-ttu-id="b2a5d-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b2a5d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b2a5d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2a5d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2a5d-105">Egy megadott műveletet késleltetve alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="b2a5d-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b2a5d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b2a5d-106">Description</span></span>

<span data-ttu-id="b2a5d-107">Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="b2a5d-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="b2a5d-108">A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="b2a5d-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="b2a5d-109">`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .</span><span class="sxs-lookup"><span data-stu-id="b2a5d-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="b2a5d-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b2a5d-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="b2a5d-111">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2a5d-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b2a5d-112">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="b2a5d-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="b2a5d-113">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="b2a5d-113">arg : 'T</span></span>

<span data-ttu-id="b2a5d-114">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="b2a5d-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="b2a5d-115">AUX: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2a5d-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="b2a5d-116">A művelet alkalmazásának a részleges alkalmazás használatával történő késleltetésére szolgáló argumentum.</span><span class="sxs-lookup"><span data-stu-id="b2a5d-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2a5d-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2a5d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b2a5d-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b2a5d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2a5d-119">Nem</span><span class="sxs-lookup"><span data-stu-id="b2a5d-119">'T</span></span>

<span data-ttu-id="b2a5d-120">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="b2a5d-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2a5d-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b2a5d-121">See Also</span></span>

- [<span data-ttu-id="b2a5d-122">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="b2a5d-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="b2a5d-123">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="b2a5d-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)