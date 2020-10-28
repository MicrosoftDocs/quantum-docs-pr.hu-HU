---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: ApplyIfElseB művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718217"
---
# <a name="applyifelseb-operation"></a><span data-ttu-id="6ab21-102">ApplyIfElseB művelet</span><span class="sxs-lookup"><span data-stu-id="6ab21-102">ApplyIfElseB operation</span></span>

<span data-ttu-id="6ab21-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ab21-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ab21-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6ab21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6ab21-105">A klasszikus bit értékétől függően két művelet egyikét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="6ab21-105">Applies one of two operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="6ab21-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6ab21-106">Description</span></span>

<span data-ttu-id="6ab21-107">Adott `bit` esetben a műveletet a `trueOp` bemenetként alkalmazza, ha a `trueInput` `bit` értéke `true` , és `falseOp(falseInput)` Ha a értéke, akkor alkalmazza `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="6ab21-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="6ab21-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6ab21-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="6ab21-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ab21-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ab21-110">A logikai érték, amellyel megállapítható, hogy `trueOp` alkalmazva van-e vagy sem `falseOp` .</span><span class="sxs-lookup"><span data-stu-id="6ab21-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit"></a><span data-ttu-id="6ab21-111">trueOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ab21-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6ab21-112">Az alkalmazásakor alkalmazandó művelet `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="6ab21-112">The operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="6ab21-113">trueInput: nem</span><span class="sxs-lookup"><span data-stu-id="6ab21-113">trueInput : 'T</span></span>

<span data-ttu-id="6ab21-114">A következőhöz megadott bemenet: `trueOp` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="6ab21-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit"></a><span data-ttu-id="6ab21-115">falseOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ab21-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6ab21-116">Az alkalmazásakor alkalmazandó művelet `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="6ab21-116">The operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="6ab21-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="6ab21-117">falseInput : 'U</span></span>

<span data-ttu-id="6ab21-118">A következőhöz megadott bemenet: `falseOp` `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="6ab21-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ab21-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ab21-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6ab21-120">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6ab21-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ab21-121">Nem</span><span class="sxs-lookup"><span data-stu-id="6ab21-121">'T</span></span>

<span data-ttu-id="6ab21-122">A `trueOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6ab21-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="6ab21-123">' U</span><span class="sxs-lookup"><span data-stu-id="6ab21-123">'U</span></span>

<span data-ttu-id="6ab21-124">A `falseOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6ab21-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ab21-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6ab21-125">See Also</span></span>

- [<span data-ttu-id="6ab21-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="6ab21-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="6ab21-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="6ab21-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="6ab21-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="6ab21-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="6ab21-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="6ab21-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="6ab21-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="6ab21-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)