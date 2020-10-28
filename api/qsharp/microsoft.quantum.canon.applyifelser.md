---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 78c1cf23614fbb7c27122548de487c7350467948
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718162"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="c0c1e-102">ApplyIfElseR művelet</span><span class="sxs-lookup"><span data-stu-id="c0c1e-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="c0c1e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0c1e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0c1e-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0c1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0c1e-105">A klasszikus eredmények értékétől függően két művelet egyikét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="c0c1e-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="c0c1e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="c0c1e-106">Description</span></span>

<span data-ttu-id="c0c1e-107">Az eredmény megadásakor `result` a műveletet a `zeroOp` `zeroInput` bemenetként alkalmazza, ha `result` az egyenlő `Zero` , és ha van, `oneOp(oneInput)` akkor alkalmazza `result == One` .</span><span class="sxs-lookup"><span data-stu-id="c0c1e-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="c0c1e-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c0c1e-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="c0c1e-109">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="c0c1e-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="c0c1e-110">Az a mérési eredmény, amellyel meghatározható, hogy `zeroOp` alkalmazva van-e vagy sem `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="c0c1e-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="c0c1e-111">zeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0c1e-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c0c1e-112">Az a művelet, amelyre alkalmazni kell `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="c0c1e-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="c0c1e-113">zeroInput: nem</span><span class="sxs-lookup"><span data-stu-id="c0c1e-113">zeroInput : 'T</span></span>

<span data-ttu-id="c0c1e-114">Az a bemenet, amelyet meg kell adni `zeroOp` `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="c0c1e-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="c0c1e-115">oneOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0c1e-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c0c1e-116">Az a művelet, amelyre alkalmazni kell `result == One` .</span><span class="sxs-lookup"><span data-stu-id="c0c1e-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="c0c1e-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="c0c1e-117">oneInput : 'U</span></span>

<span data-ttu-id="c0c1e-118">Az a bemenet, amelyet meg kell adni `oneOp` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="c0c1e-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0c1e-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0c1e-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c0c1e-120">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c0c1e-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c0c1e-121">Nem</span><span class="sxs-lookup"><span data-stu-id="c0c1e-121">'T</span></span>

<span data-ttu-id="c0c1e-122">A `zeroOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="c0c1e-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="c0c1e-123">' U</span><span class="sxs-lookup"><span data-stu-id="c0c1e-123">'U</span></span>

<span data-ttu-id="c0c1e-124">A `oneOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="c0c1e-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0c1e-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c0c1e-125">See Also</span></span>

- [<span data-ttu-id="c0c1e-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="c0c1e-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="c0c1e-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="c0c1e-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="c0c1e-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="c0c1e-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="c0c1e-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="c0c1e-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="c0c1e-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="c0c1e-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)