---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: ApplyIfElseRCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: dfd1c16a25a2da507024813a380386c8f4e49d30
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218750"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="09eee-102">ApplyIfElseRCA művelet</span><span class="sxs-lookup"><span data-stu-id="09eee-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="09eee-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09eee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09eee-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09eee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09eee-105">A klasszikus találatok értékétől függően két egységes művelet egyikét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="09eee-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="09eee-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="09eee-106">Description</span></span>

<span data-ttu-id="09eee-107">Az eredmény megadásakor `result` a műveletet a `zeroOp` `zeroInput` bemenetként alkalmazza, ha `result` az egyenlő `Zero` , és ha van, `oneOp(oneInput)` akkor alkalmazza `result == One` .</span><span class="sxs-lookup"><span data-stu-id="09eee-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="09eee-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="09eee-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="09eee-109">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="09eee-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="09eee-110">Az a mérési eredmény, amellyel meghatározható, hogy `zeroOp` alkalmazva van-e vagy sem `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="09eee-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="09eee-111">zeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="09eee-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="09eee-112">Az az egységes művelet, amelyre alkalmazni kell `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="09eee-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="09eee-113">zeroInput: nem</span><span class="sxs-lookup"><span data-stu-id="09eee-113">zeroInput : 'T</span></span>

<span data-ttu-id="09eee-114">Az a bemenet, amelyet meg kell adni `zeroOp` `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="09eee-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj--ctl"></a><span data-ttu-id="09eee-115">oneOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="09eee-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="09eee-116">Az az egységes művelet, amelyre alkalmazni kell `result == One` .</span><span class="sxs-lookup"><span data-stu-id="09eee-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="09eee-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="09eee-117">oneInput : 'U</span></span>

<span data-ttu-id="09eee-118">Az a bemenet, amelyet meg kell adni `oneOp` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="09eee-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09eee-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09eee-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="09eee-120">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="09eee-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09eee-121">Nem</span><span class="sxs-lookup"><span data-stu-id="09eee-121">'T</span></span>

<span data-ttu-id="09eee-122">A `zeroOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="09eee-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="09eee-123">' U</span><span class="sxs-lookup"><span data-stu-id="09eee-123">'U</span></span>

<span data-ttu-id="09eee-124">A `oneOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="09eee-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="09eee-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="09eee-125">See Also</span></span>

- [<span data-ttu-id="09eee-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="09eee-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="09eee-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="09eee-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="09eee-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="09eee-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="09eee-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="09eee-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="09eee-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="09eee-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)