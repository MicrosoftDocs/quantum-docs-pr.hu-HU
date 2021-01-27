---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: ebeec5b46567892ad30f194ababb42876ba08bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841757"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="fa487-102">ApplyIfOneC művelet</span><span class="sxs-lookup"><span data-stu-id="fa487-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="fa487-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fa487-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fa487-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa487-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa487-105">Egy, a klasszikus eredmény értékének egyikét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="fa487-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="fa487-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="fa487-106">Description</span></span>

<span data-ttu-id="fa487-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="fa487-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="fa487-108">Ha `Zero` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="fa487-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="fa487-109">Az utótag `C` azt jelzi, hogy az alkalmazni kívánt művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="fa487-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="fa487-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fa487-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="fa487-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="fa487-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="fa487-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="fa487-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="fa487-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="fa487-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="fa487-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="fa487-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="fa487-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="fa487-115">target : 'T</span></span>

<span data-ttu-id="fa487-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="fa487-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa487-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa487-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fa487-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="fa487-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa487-119">Nem</span><span class="sxs-lookup"><span data-stu-id="fa487-119">'T</span></span>

<span data-ttu-id="fa487-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="fa487-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa487-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fa487-121">See Also</span></span>

- [<span data-ttu-id="fa487-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="fa487-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="fa487-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="fa487-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="fa487-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="fa487-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)