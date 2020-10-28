---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: ApplyIfZeroA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: d324cd970e8df49ceb51b6bf5c9f3c9c3ff142f9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718051"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="3d802-102">ApplyIfZeroA művelet</span><span class="sxs-lookup"><span data-stu-id="3d802-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="3d802-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3d802-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3d802-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3d802-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3d802-105">Egy olyan adjointable műveletet alkalmaz, amely klasszikus eredmény értéke nulla.</span><span class="sxs-lookup"><span data-stu-id="3d802-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="3d802-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="3d802-106">Description</span></span>

<span data-ttu-id="3d802-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="3d802-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="3d802-108">Ha `One` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="3d802-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3d802-109">Az utótag `A` azt jelzi, hogy az alkalmazni kívánt művelet a adjointable.</span><span class="sxs-lookup"><span data-stu-id="3d802-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="3d802-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3d802-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3d802-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="3d802-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="3d802-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="3d802-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="3d802-113">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="3d802-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3d802-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="3d802-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3d802-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="3d802-115">target : 'T</span></span>

<span data-ttu-id="3d802-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="3d802-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3d802-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d802-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3d802-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3d802-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3d802-119">Nem</span><span class="sxs-lookup"><span data-stu-id="3d802-119">'T</span></span>

<span data-ttu-id="3d802-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="3d802-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d802-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3d802-121">See Also</span></span>

- [<span data-ttu-id="3d802-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="3d802-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="3d802-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="3d802-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="3d802-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="3d802-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)