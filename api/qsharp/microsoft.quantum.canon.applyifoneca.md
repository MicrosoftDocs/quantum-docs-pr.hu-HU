---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 973dd3c5f9f3e9ad03c0626a38779f499b7ce657
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718065"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="9a968-102">ApplyIfOneCA művelet</span><span class="sxs-lookup"><span data-stu-id="9a968-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="9a968-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a968-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a968-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a968-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a968-105">A klasszikus eredmény értékeként egy egységes műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="9a968-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="9a968-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="9a968-106">Description</span></span>

<span data-ttu-id="9a968-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="9a968-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="9a968-108">Ha `Zero` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="9a968-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="9a968-109">Az utótag `CA` azt jelzi, hogy az alkalmazni kívánt művelet egységes (ellenőrizhető és adjointable).</span><span class="sxs-lookup"><span data-stu-id="9a968-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="9a968-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9a968-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9a968-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="9a968-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="9a968-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="9a968-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="9a968-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9a968-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9a968-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="9a968-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="9a968-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="9a968-115">target : 'T</span></span>

<span data-ttu-id="9a968-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="9a968-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a968-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a968-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a968-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9a968-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a968-119">Nem</span><span class="sxs-lookup"><span data-stu-id="9a968-119">'T</span></span>

<span data-ttu-id="9a968-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="9a968-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a968-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="9a968-121">See Also</span></span>

- [<span data-ttu-id="9a968-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="9a968-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="9a968-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="9a968-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="9a968-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="9a968-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)