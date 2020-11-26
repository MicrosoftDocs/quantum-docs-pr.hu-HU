---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217339"
---
# <a name="applytohead-operation"></a><span data-ttu-id="d63f7-102">ApplyToHead művelet</span><span class="sxs-lookup"><span data-stu-id="d63f7-102">ApplyToHead operation</span></span>

<span data-ttu-id="d63f7-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d63f7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d63f7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d63f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d63f7-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="d63f7-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d63f7-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d63f7-106">Description</span></span>

<span data-ttu-id="d63f7-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d63f7-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d63f7-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d63f7-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d63f7-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d63f7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d63f7-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="d63f7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d63f7-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="d63f7-111">targets : 'T[]</span></span>

<span data-ttu-id="d63f7-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="d63f7-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d63f7-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d63f7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d63f7-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d63f7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d63f7-115">Nem</span><span class="sxs-lookup"><span data-stu-id="d63f7-115">'T</span></span>

<span data-ttu-id="d63f7-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="d63f7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d63f7-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d63f7-117">See Also</span></span>

- [<span data-ttu-id="d63f7-118">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="d63f7-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="d63f7-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="d63f7-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="d63f7-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="d63f7-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)