---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218580"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="2c67d-102">ApplyIfOneCA művelet</span><span class="sxs-lookup"><span data-stu-id="2c67d-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="2c67d-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c67d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c67d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c67d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c67d-105">A klasszikus eredmény értékeként egy egységes műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="2c67d-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2c67d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2c67d-106">Description</span></span>

<span data-ttu-id="2c67d-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="2c67d-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="2c67d-108">Ha `Zero` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="2c67d-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="2c67d-109">Az utótag `CA` azt jelzi, hogy az alkalmazni kívánt művelet egységes (ellenőrizhető és adjointable).</span><span class="sxs-lookup"><span data-stu-id="2c67d-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="2c67d-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2c67d-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="2c67d-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="2c67d-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="2c67d-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="2c67d-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="2c67d-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2c67d-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2c67d-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="2c67d-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="2c67d-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="2c67d-115">target : 'T</span></span>

<span data-ttu-id="2c67d-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2c67d-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c67d-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c67d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c67d-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2c67d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c67d-119">Nem</span><span class="sxs-lookup"><span data-stu-id="2c67d-119">'T</span></span>

<span data-ttu-id="2c67d-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2c67d-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c67d-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2c67d-121">See Also</span></span>

- [<span data-ttu-id="2c67d-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="2c67d-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="2c67d-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="2c67d-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="2c67d-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="2c67d-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)