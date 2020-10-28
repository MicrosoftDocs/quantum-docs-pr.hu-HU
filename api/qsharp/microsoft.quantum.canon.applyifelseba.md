---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: ce08907646c3210f76244f29aa0d936e2bd6ee43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718204"
---
# <a name="applyifelseba-operation"></a><span data-ttu-id="4a03c-102">ApplyIfElseBA művelet</span><span class="sxs-lookup"><span data-stu-id="4a03c-102">ApplyIfElseBA operation</span></span>

<span data-ttu-id="4a03c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a03c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a03c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a03c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a03c-105">Egy klasszikus bit értékétől függően két adjointable műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="4a03c-105">Applies one of two adjointable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="4a03c-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4a03c-106">Description</span></span>

<span data-ttu-id="4a03c-107">Adott `bit` esetben a műveletet a `trueOp` bemenetként alkalmazza, ha a `trueInput` `bit` értéke `true` , és `falseOp(falseInput)` Ha a értéke, akkor alkalmazza `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="4a03c-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="4a03c-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4a03c-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="4a03c-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4a03c-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4a03c-110">A logikai érték, amellyel megállapítható, hogy `trueOp` alkalmazva van-e vagy sem `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="4a03c-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj"></a><span data-ttu-id="4a03c-111">trueOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="4a03c-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4a03c-112">Az adjointable művelet, amelyre alkalmazni kell `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="4a03c-112">The adjointable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="4a03c-113">trueInput: nem</span><span class="sxs-lookup"><span data-stu-id="4a03c-113">trueInput : 'T</span></span>

<span data-ttu-id="4a03c-114">A következőhöz megadott bemenet: `trueOp` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="4a03c-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj"></a><span data-ttu-id="4a03c-115">falseOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="4a03c-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4a03c-116">Az adjointable művelet, amelyre alkalmazni kell `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="4a03c-116">The adjointable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="4a03c-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="4a03c-117">falseInput : 'U</span></span>

<span data-ttu-id="4a03c-118">A következőhöz megadott bemenet: `falseOp` `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="4a03c-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a03c-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a03c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a03c-120">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4a03c-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a03c-121">Nem</span><span class="sxs-lookup"><span data-stu-id="4a03c-121">'T</span></span>

<span data-ttu-id="4a03c-122">A `trueOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="4a03c-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="4a03c-123">' U</span><span class="sxs-lookup"><span data-stu-id="4a03c-123">'U</span></span>

<span data-ttu-id="4a03c-124">A `falseOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="4a03c-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a03c-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4a03c-125">See Also</span></span>

- [<span data-ttu-id="4a03c-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="4a03c-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="4a03c-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="4a03c-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="4a03c-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="4a03c-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="4a03c-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="4a03c-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="4a03c-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="4a03c-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)