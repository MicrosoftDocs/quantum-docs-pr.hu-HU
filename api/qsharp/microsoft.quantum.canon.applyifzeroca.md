---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: ApplyIfZeroCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 85612bd3dd7af45b7901fef775a7d556eb229608
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718008"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="b7121-102">ApplyIfZeroCA művelet</span><span class="sxs-lookup"><span data-stu-id="b7121-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="b7121-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b7121-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b7121-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7121-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7121-105">A klasszikus eredmény értékének nulla értékű, egységes műveletét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="b7121-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="b7121-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b7121-106">Description</span></span>

<span data-ttu-id="b7121-107">`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="b7121-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="b7121-108">Ha `One` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="b7121-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="b7121-109">Az utótag `CA` azt jelzi, hogy az alkalmazni kívánt művelet egységes (ellenőrizhető és adjointable).</span><span class="sxs-lookup"><span data-stu-id="b7121-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="b7121-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b7121-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b7121-111">eredmény: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="b7121-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="b7121-112">Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="b7121-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="b7121-113">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="b7121-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b7121-114">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="b7121-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="b7121-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="b7121-115">target : 'T</span></span>

<span data-ttu-id="b7121-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="b7121-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7121-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7121-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b7121-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b7121-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b7121-119">Nem</span><span class="sxs-lookup"><span data-stu-id="b7121-119">'T</span></span>

<span data-ttu-id="b7121-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="b7121-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7121-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b7121-121">See Also</span></span>

- [<span data-ttu-id="b7121-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="b7121-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="b7121-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="b7121-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="b7121-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="b7121-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)