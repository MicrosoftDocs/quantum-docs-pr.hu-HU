---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208635"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="1384e-102">ApplyToHeadA művelet</span><span class="sxs-lookup"><span data-stu-id="1384e-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="1384e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1384e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1384e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1384e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1384e-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="1384e-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="1384e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="1384e-106">Description</span></span>

<span data-ttu-id="1384e-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="1384e-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="1384e-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1384e-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="1384e-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1384e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1384e-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="1384e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1384e-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="1384e-111">targets : 'T[]</span></span>

<span data-ttu-id="1384e-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="1384e-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1384e-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1384e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1384e-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1384e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1384e-115">Nem</span><span class="sxs-lookup"><span data-stu-id="1384e-115">'T</span></span>

<span data-ttu-id="1384e-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="1384e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1384e-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="1384e-117">See Also</span></span>

- [<span data-ttu-id="1384e-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="1384e-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="1384e-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="1384e-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="1384e-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="1384e-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)