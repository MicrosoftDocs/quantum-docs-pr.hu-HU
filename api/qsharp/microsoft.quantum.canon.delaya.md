---
uid: Microsoft.Quantum.Canon.DelayA
title: Késleltetési művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c7385cfcdf782347feb8d95311205a9311f4c929
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840670"
---
# <a name="delaya-operation"></a><span data-ttu-id="35700-102">Késleltetési művelet</span><span class="sxs-lookup"><span data-stu-id="35700-102">DelayA operation</span></span>

<span data-ttu-id="35700-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="35700-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="35700-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35700-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35700-105">Egy megadott műveletet késleltetve alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="35700-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="35700-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="35700-106">Description</span></span>

<span data-ttu-id="35700-107">Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.</span><span class="sxs-lookup"><span data-stu-id="35700-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="35700-108">A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="35700-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="35700-109">`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .</span><span class="sxs-lookup"><span data-stu-id="35700-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="35700-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="35700-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="35700-111">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35700-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="35700-112">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="35700-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="35700-113">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="35700-113">arg : 'T</span></span>

<span data-ttu-id="35700-114">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="35700-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="35700-115">AUX: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35700-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="35700-116">A művelet alkalmazásának a részleges alkalmazás használatával történő késleltetésére szolgáló argumentum.</span><span class="sxs-lookup"><span data-stu-id="35700-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35700-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35700-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="35700-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="35700-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35700-119">Nem</span><span class="sxs-lookup"><span data-stu-id="35700-119">'T</span></span>

<span data-ttu-id="35700-120">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="35700-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="35700-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="35700-121">See Also</span></span>

- [<span data-ttu-id="35700-122">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="35700-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="35700-123">Microsoft. Quantum. Canon. késleltetve</span><span class="sxs-lookup"><span data-stu-id="35700-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)