---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3876e2baf1b3ad5bbfa0097d468b1e88adf05db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841720"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="08ff1-102">ApplyIfZeroC művelet</span><span class="sxs-lookup"><span data-stu-id="08ff1-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="08ff1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="08ff1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="08ff1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08ff1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08ff1-105">Egy, a klasszikus eredmény értékének nulla értékét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="08ff1-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="08ff1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="08ff1-106">Description</span></span>

<span data-ttu-id="08ff1-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="08ff1-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="08ff1-108">Ha `One` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="08ff1-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="08ff1-109">Az utótag `C` azt jelzi, hogy az alkalmazni kívánt művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="08ff1-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="08ff1-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="08ff1-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="08ff1-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="08ff1-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="08ff1-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="08ff1-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="08ff1-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="08ff1-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="08ff1-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="08ff1-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="08ff1-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="08ff1-115">target : 'T</span></span>

<span data-ttu-id="08ff1-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="08ff1-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="08ff1-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="08ff1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="08ff1-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="08ff1-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="08ff1-119">Nem</span><span class="sxs-lookup"><span data-stu-id="08ff1-119">'T</span></span>

<span data-ttu-id="08ff1-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="08ff1-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="08ff1-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="08ff1-121">See Also</span></span>

- [<span data-ttu-id="08ff1-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="08ff1-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="08ff1-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="08ff1-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="08ff1-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="08ff1-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)