---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218767"
---
# <a name="applyifa-operation"></a><span data-ttu-id="8b5e4-102">ApplyIfA művelet</span><span class="sxs-lookup"><span data-stu-id="8b5e4-102">ApplyIfA operation</span></span>

<span data-ttu-id="8b5e4-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8b5e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8b5e4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b5e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b5e4-105">Egy klasszikus bites adjointable műveletet alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="8b5e4-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="8b5e4-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8b5e4-106">Description</span></span>

<span data-ttu-id="8b5e4-107">Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8b5e4-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="8b5e4-108">Ha `false` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="8b5e4-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="8b5e4-109">Az utótag `A` azt jelzi, hogy az alkalmazni kívánt művelet a adjointable.</span><span class="sxs-lookup"><span data-stu-id="8b5e4-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="8b5e4-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8b5e4-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="8b5e4-111">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b5e4-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8b5e4-112">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="8b5e4-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="8b5e4-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8b5e4-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8b5e4-114">egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="8b5e4-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="8b5e4-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="8b5e4-115">target : 'T</span></span>

<span data-ttu-id="8b5e4-116">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="8b5e4-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b5e4-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b5e4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8b5e4-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8b5e4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b5e4-119">Nem</span><span class="sxs-lookup"><span data-stu-id="8b5e4-119">'T</span></span>

<span data-ttu-id="8b5e4-120">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="8b5e4-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b5e4-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8b5e4-121">See Also</span></span>

- [<span data-ttu-id="8b5e4-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="8b5e4-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="8b5e4-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="8b5e4-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="8b5e4-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="8b5e4-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)