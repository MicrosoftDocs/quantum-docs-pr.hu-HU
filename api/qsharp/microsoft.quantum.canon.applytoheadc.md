---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208601"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="df4f2-102">ApplyToHeadC művelet</span><span class="sxs-lookup"><span data-stu-id="df4f2-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="df4f2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="df4f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="df4f2-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df4f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df4f2-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="df4f2-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="df4f2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="df4f2-106">Description</span></span>

<span data-ttu-id="df4f2-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="df4f2-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="df4f2-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df4f2-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="df4f2-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="df4f2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="df4f2-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="df4f2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="df4f2-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="df4f2-111">targets : 'T[]</span></span>

<span data-ttu-id="df4f2-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="df4f2-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df4f2-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df4f2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="df4f2-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="df4f2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="df4f2-115">Nem</span><span class="sxs-lookup"><span data-stu-id="df4f2-115">'T</span></span>

<span data-ttu-id="df4f2-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="df4f2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="df4f2-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="df4f2-117">See Also</span></span>

- [<span data-ttu-id="df4f2-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="df4f2-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="df4f2-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="df4f2-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="df4f2-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="df4f2-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)