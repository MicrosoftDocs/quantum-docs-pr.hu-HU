---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717238"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="e7ff2-102">ApplyToHeadCA művelet</span><span class="sxs-lookup"><span data-stu-id="e7ff2-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="e7ff2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e7ff2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e7ff2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7ff2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7ff2-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="e7ff2-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e7ff2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e7ff2-106">Description</span></span>

<span data-ttu-id="e7ff2-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e7ff2-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e7ff2-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e7ff2-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="e7ff2-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="e7ff2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e7ff2-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="e7ff2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e7ff2-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="e7ff2-111">targets : 'T[]</span></span>

<span data-ttu-id="e7ff2-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="e7ff2-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7ff2-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7ff2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e7ff2-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e7ff2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e7ff2-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e7ff2-115">'T</span></span>

<span data-ttu-id="e7ff2-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="e7ff2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7ff2-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e7ff2-117">See Also</span></span>

- [<span data-ttu-id="e7ff2-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="e7ff2-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="e7ff2-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="e7ff2-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="e7ff2-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="e7ff2-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)