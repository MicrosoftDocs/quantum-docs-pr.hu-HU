---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718009"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="c4372-102">ApplyIfZeroC művelet</span><span class="sxs-lookup"><span data-stu-id="c4372-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="c4372-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4372-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4372-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4372-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4372-105">Egy, a klasszikus eredmény értékének nulla értékét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="c4372-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="c4372-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="c4372-106">Description</span></span>

<span data-ttu-id="c4372-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="c4372-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="c4372-108">Ha `One` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="c4372-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="c4372-109">Az utótag `C` azt jelzi, hogy az alkalmazni kívánt művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="c4372-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="c4372-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c4372-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="c4372-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="c4372-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="c4372-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="c4372-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="c4372-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="c4372-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c4372-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="c4372-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="c4372-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="c4372-115">target : 'T</span></span>

<span data-ttu-id="c4372-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="c4372-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4372-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4372-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c4372-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c4372-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4372-119">Nem</span><span class="sxs-lookup"><span data-stu-id="c4372-119">'T</span></span>

<span data-ttu-id="c4372-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="c4372-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4372-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c4372-121">See Also</span></span>

- [<span data-ttu-id="c4372-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="c4372-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="c4372-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="c4372-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="c4372-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="c4372-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)