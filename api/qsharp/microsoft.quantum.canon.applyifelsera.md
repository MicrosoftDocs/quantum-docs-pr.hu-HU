---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: ApplyIfElseRA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 3ebd09b1e5876ff397f3524ba828ba26a271e91e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218597"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="7bf92-102">ApplyIfElseRA művelet</span><span class="sxs-lookup"><span data-stu-id="7bf92-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="7bf92-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7bf92-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7bf92-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7bf92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7bf92-105">Egy klasszikus eredmény értékétől függően két adjointable műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="7bf92-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="7bf92-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="7bf92-106">Description</span></span>

<span data-ttu-id="7bf92-107">Az eredmény megadásakor `result` a műveletet a `zeroOp` `zeroInput` bemenetként alkalmazza, ha `result` az egyenlő `Zero` , és ha van, `oneOp(oneInput)` akkor alkalmazza `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7bf92-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="7bf92-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7bf92-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7bf92-109">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="7bf92-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="7bf92-110">Az a mérési eredmény, amellyel meghatározható, hogy `zeroOp` alkalmazva van-e vagy sem `oneOp` .</span><span class="sxs-lookup"><span data-stu-id="7bf92-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj"></a><span data-ttu-id="7bf92-111">zeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bf92-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7bf92-112">A adjointable művelet, amelyre alkalmazni kell `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="7bf92-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="7bf92-113">zeroInput: nem</span><span class="sxs-lookup"><span data-stu-id="7bf92-113">zeroInput : 'T</span></span>

<span data-ttu-id="7bf92-114">Az a bemenet, amelyet meg kell adni `zeroOp` `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="7bf92-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj"></a><span data-ttu-id="7bf92-115">oneOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bf92-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7bf92-116">A adjointable művelet, amelyre alkalmazni kell `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7bf92-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="7bf92-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="7bf92-117">oneInput : 'U</span></span>

<span data-ttu-id="7bf92-118">Az a bemenet, amelyet meg kell adni `oneOp` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="7bf92-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7bf92-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bf92-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7bf92-120">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7bf92-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7bf92-121">Nem</span><span class="sxs-lookup"><span data-stu-id="7bf92-121">'T</span></span>

<span data-ttu-id="7bf92-122">A `zeroOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="7bf92-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="7bf92-123">' U</span><span class="sxs-lookup"><span data-stu-id="7bf92-123">'U</span></span>

<span data-ttu-id="7bf92-124">A `oneOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="7bf92-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bf92-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7bf92-125">See Also</span></span>

- [<span data-ttu-id="7bf92-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="7bf92-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="7bf92-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="7bf92-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="7bf92-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="7bf92-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="7bf92-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="7bf92-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="7bf92-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="7bf92-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)