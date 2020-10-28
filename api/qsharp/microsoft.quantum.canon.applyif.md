---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718241"
---
# <a name="applyif-operation"></a><span data-ttu-id="964bb-102">ApplyIf művelet</span><span class="sxs-lookup"><span data-stu-id="964bb-102">ApplyIf operation</span></span>

<span data-ttu-id="964bb-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="964bb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="964bb-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="964bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="964bb-105">Egy klasszikus bites műveletre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="964bb-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="964bb-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="964bb-106">Description</span></span>

<span data-ttu-id="964bb-107">Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="964bb-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="964bb-108">Ha `false` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="964bb-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="964bb-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="964bb-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="964bb-110">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="964bb-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="964bb-111">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="964bb-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="964bb-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="964bb-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="964bb-113">egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="964bb-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="964bb-114">cél: nem</span><span class="sxs-lookup"><span data-stu-id="964bb-114">target : 'T</span></span>

<span data-ttu-id="964bb-115">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="964bb-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="964bb-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="964bb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="964bb-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="964bb-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="964bb-118">Nem</span><span class="sxs-lookup"><span data-stu-id="964bb-118">'T</span></span>

<span data-ttu-id="964bb-119">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="964bb-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="964bb-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="964bb-120">See Also</span></span>

- [<span data-ttu-id="964bb-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="964bb-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="964bb-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="964bb-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="964bb-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="964bb-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)