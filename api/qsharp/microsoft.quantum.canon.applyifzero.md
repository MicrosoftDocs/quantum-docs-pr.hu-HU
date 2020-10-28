---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718064"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="bd349-102">ApplyIfZero művelet</span><span class="sxs-lookup"><span data-stu-id="bd349-102">ApplyIfZero operation</span></span>

<span data-ttu-id="bd349-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd349-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd349-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd349-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd349-105">Egy klasszikus eredmény értékének nulla értékű műveletét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="bd349-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="bd349-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="bd349-106">Description</span></span>

<span data-ttu-id="bd349-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="bd349-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="bd349-108">Ha `One` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="bd349-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="bd349-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bd349-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="bd349-110">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="bd349-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="bd349-111">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="bd349-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="bd349-112">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd349-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bd349-113">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="bd349-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="bd349-114">cél: nem</span><span class="sxs-lookup"><span data-stu-id="bd349-114">target : 'T</span></span>

<span data-ttu-id="bd349-115">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="bd349-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd349-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd349-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bd349-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bd349-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd349-118">Nem</span><span class="sxs-lookup"><span data-stu-id="bd349-118">'T</span></span>

<span data-ttu-id="bd349-119">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="bd349-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd349-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bd349-120">See Also</span></span>

- [<span data-ttu-id="bd349-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="bd349-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="bd349-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="bd349-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="bd349-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="bd349-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)