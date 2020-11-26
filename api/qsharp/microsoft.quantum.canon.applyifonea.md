---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 200908f2958b74e4823c891ef901474d75d18336
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218546"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="80c4e-102">ApplyIfOneA művelet</span><span class="sxs-lookup"><span data-stu-id="80c4e-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="80c4e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80c4e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80c4e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80c4e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80c4e-105">Egy olyan adjointable műveletet alkalmaz, amely egy klasszikus eredmény értéke egy.</span><span class="sxs-lookup"><span data-stu-id="80c4e-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="80c4e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="80c4e-106">Description</span></span>

<span data-ttu-id="80c4e-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="80c4e-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="80c4e-108">Ha `Zero` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="80c4e-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="80c4e-109">Az utótag `A` azt jelzi, hogy az alkalmazni kívánt művelet a adjointable.</span><span class="sxs-lookup"><span data-stu-id="80c4e-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="80c4e-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="80c4e-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="80c4e-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="80c4e-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="80c4e-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="80c4e-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="80c4e-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80c4e-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="80c4e-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="80c4e-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="80c4e-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="80c4e-115">target : 'T</span></span>

<span data-ttu-id="80c4e-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="80c4e-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80c4e-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80c4e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="80c4e-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="80c4e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80c4e-119">Nem</span><span class="sxs-lookup"><span data-stu-id="80c4e-119">'T</span></span>

<span data-ttu-id="80c4e-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="80c4e-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="80c4e-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="80c4e-121">See Also</span></span>

- [<span data-ttu-id="80c4e-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="80c4e-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="80c4e-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="80c4e-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="80c4e-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="80c4e-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)