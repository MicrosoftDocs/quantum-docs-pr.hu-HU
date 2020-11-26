---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218835"
---
# <a name="applyif-operation"></a><span data-ttu-id="dd7ed-102">ApplyIf művelet</span><span class="sxs-lookup"><span data-stu-id="dd7ed-102">ApplyIf operation</span></span>

<span data-ttu-id="dd7ed-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd7ed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd7ed-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd7ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd7ed-105">Egy klasszikus bites műveletre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="dd7ed-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="dd7ed-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="dd7ed-106">Description</span></span>

<span data-ttu-id="dd7ed-107">Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="dd7ed-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="dd7ed-108">Ha `false` semmi nem történik a következővel: `target` .</span><span class="sxs-lookup"><span data-stu-id="dd7ed-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="dd7ed-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dd7ed-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="dd7ed-110">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd7ed-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="dd7ed-111">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="dd7ed-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="dd7ed-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dd7ed-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dd7ed-113">egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.</span><span class="sxs-lookup"><span data-stu-id="dd7ed-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="dd7ed-114">cél: nem</span><span class="sxs-lookup"><span data-stu-id="dd7ed-114">target : 'T</span></span>

<span data-ttu-id="dd7ed-115">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="dd7ed-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd7ed-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd7ed-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dd7ed-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dd7ed-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dd7ed-118">Nem</span><span class="sxs-lookup"><span data-stu-id="dd7ed-118">'T</span></span>

<span data-ttu-id="dd7ed-119">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="dd7ed-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd7ed-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="dd7ed-120">See Also</span></span>

- [<span data-ttu-id="dd7ed-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="dd7ed-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="dd7ed-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="dd7ed-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="dd7ed-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="dd7ed-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)