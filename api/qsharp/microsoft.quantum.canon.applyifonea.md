---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844931"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="76357-102">ApplyIfOneA művelet</span><span class="sxs-lookup"><span data-stu-id="76357-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="76357-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76357-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76357-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76357-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76357-105">Egy olyan adjointable műveletet alkalmaz, amely egy klasszikus eredmény értéke egy.</span><span class="sxs-lookup"><span data-stu-id="76357-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="76357-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="76357-106">Description</span></span>

<span data-ttu-id="76357-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="76357-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="76357-108">Ha `Zero` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="76357-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="76357-109">Az utótag `A` azt jelzi, hogy az alkalmazni kívánt művelet a adjointable.</span><span class="sxs-lookup"><span data-stu-id="76357-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="76357-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="76357-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="76357-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="76357-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="76357-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="76357-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="76357-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76357-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="76357-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="76357-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="76357-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="76357-115">target : 'T</span></span>

<span data-ttu-id="76357-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="76357-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76357-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76357-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="76357-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="76357-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76357-119">Nem</span><span class="sxs-lookup"><span data-stu-id="76357-119">'T</span></span>

<span data-ttu-id="76357-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="76357-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="76357-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="76357-121">See Also</span></span>

- [<span data-ttu-id="76357-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="76357-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="76357-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="76357-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="76357-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="76357-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)