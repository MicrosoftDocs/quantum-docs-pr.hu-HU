---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b7c07e01ebcaf2d475283bea0695aa68dd10776e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209400"
---
# <a name="applyifone-operation"></a><span data-ttu-id="c78f3-102">ApplyIfOne művelet</span><span class="sxs-lookup"><span data-stu-id="c78f3-102">ApplyIfOne operation</span></span>

<span data-ttu-id="c78f3-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c78f3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c78f3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c78f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c78f3-105">Egy olyan műveletet alkalmaz, amely egy klasszikus eredmény értéke egy.</span><span class="sxs-lookup"><span data-stu-id="c78f3-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="c78f3-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="c78f3-106">Description</span></span>

<span data-ttu-id="c78f3-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` .</span><span class="sxs-lookup"><span data-stu-id="c78f3-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="c78f3-108">Ha `Zero` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="c78f3-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="c78f3-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c78f3-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="c78f3-110">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="c78f3-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="c78f3-111">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="c78f3-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="c78f3-112">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c78f3-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c78f3-113">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="c78f3-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="c78f3-114">cél: nem</span><span class="sxs-lookup"><span data-stu-id="c78f3-114">target : 'T</span></span>

<span data-ttu-id="c78f3-115">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="c78f3-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c78f3-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c78f3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c78f3-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c78f3-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c78f3-118">Nem</span><span class="sxs-lookup"><span data-stu-id="c78f3-118">'T</span></span>

<span data-ttu-id="c78f3-119">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="c78f3-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c78f3-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c78f3-120">See Also</span></span>

- [<span data-ttu-id="c78f3-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="c78f3-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="c78f3-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="c78f3-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="c78f3-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="c78f3-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)