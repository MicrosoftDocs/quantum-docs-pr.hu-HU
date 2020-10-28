---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717253"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="c2a86-102">ApplyToHeadA művelet</span><span class="sxs-lookup"><span data-stu-id="c2a86-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="c2a86-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c2a86-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c2a86-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2a86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2a86-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="c2a86-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c2a86-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="c2a86-106">Description</span></span>

<span data-ttu-id="c2a86-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c2a86-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c2a86-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c2a86-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="c2a86-109">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="c2a86-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c2a86-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="c2a86-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c2a86-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="c2a86-111">targets : 'T[]</span></span>

<span data-ttu-id="c2a86-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="c2a86-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c2a86-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2a86-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c2a86-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c2a86-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2a86-115">Nem</span><span class="sxs-lookup"><span data-stu-id="c2a86-115">'T</span></span>

<span data-ttu-id="c2a86-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="c2a86-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2a86-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c2a86-117">See Also</span></span>

- [<span data-ttu-id="c2a86-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="c2a86-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="c2a86-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="c2a86-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="c2a86-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="c2a86-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)