---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718229"
---
# <a name="applyifca-operation"></a><span data-ttu-id="e4ed9-102">ApplyIfCA művelet</span><span class="sxs-lookup"><span data-stu-id="e4ed9-102">ApplyIfCA operation</span></span>

<span data-ttu-id="e4ed9-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4ed9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4ed9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4ed9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4ed9-105">Egy klasszikus bites, egységes műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="e4ed9-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="e4ed9-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e4ed9-106">Description</span></span>

<span data-ttu-id="e4ed9-107">Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="e4ed9-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="e4ed9-108">Ha `false` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="e4ed9-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e4ed9-109">Az utótag `CA` azt jelzi, hogy az alkalmazni kívánt művelet egységes (ellenőrizhető és adjointable).</span><span class="sxs-lookup"><span data-stu-id="e4ed9-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="e4ed9-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e4ed9-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="e4ed9-111">op: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="e4ed9-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="e4ed9-112">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="e4ed9-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="e4ed9-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e4ed9-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e4ed9-114">egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="e4ed9-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="e4ed9-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="e4ed9-115">target : 'T</span></span>

<span data-ttu-id="e4ed9-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="e4ed9-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e4ed9-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4ed9-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e4ed9-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e4ed9-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4ed9-119">Nem</span><span class="sxs-lookup"><span data-stu-id="e4ed9-119">'T</span></span>

<span data-ttu-id="e4ed9-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="e4ed9-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ed9-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e4ed9-121">See Also</span></span>

- [<span data-ttu-id="e4ed9-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="e4ed9-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="e4ed9-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="e4ed9-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="e4ed9-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="e4ed9-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)