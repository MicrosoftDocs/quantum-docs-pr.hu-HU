---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 9a2e020c596b02d9cb38309d02ca02056c1dec75
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718092"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="f88a2-102">ApplyIfOneC művelet</span><span class="sxs-lookup"><span data-stu-id="f88a2-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="f88a2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f88a2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f88a2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f88a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f88a2-105">Egy, a klasszikus eredmény értékének egyikét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="f88a2-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="f88a2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f88a2-106">Description</span></span>

<span data-ttu-id="f88a2-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="f88a2-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f88a2-108">Ha `Zero` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="f88a2-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f88a2-109">Az utótag `C` azt jelzi, hogy az alkalmazni kívánt művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="f88a2-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="f88a2-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f88a2-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f88a2-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="f88a2-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f88a2-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="f88a2-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="f88a2-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f88a2-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f88a2-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="f88a2-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f88a2-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="f88a2-115">target : 'T</span></span>

<span data-ttu-id="f88a2-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="f88a2-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f88a2-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f88a2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f88a2-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f88a2-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f88a2-119">Nem</span><span class="sxs-lookup"><span data-stu-id="f88a2-119">'T</span></span>

<span data-ttu-id="f88a2-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="f88a2-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f88a2-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f88a2-121">See Also</span></span>

- [<span data-ttu-id="f88a2-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f88a2-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f88a2-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="f88a2-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f88a2-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f88a2-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)