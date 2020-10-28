---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e5fc439f48a5c7e527b7805c35cce18eca3ab36
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717267"
---
# <a name="applytohead-operation"></a><span data-ttu-id="8aab1-102">ApplyToHead művelet</span><span class="sxs-lookup"><span data-stu-id="8aab1-102">ApplyToHead operation</span></span>

<span data-ttu-id="8aab1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8aab1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8aab1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8aab1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8aab1-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="8aab1-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="8aab1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8aab1-106">Description</span></span>

<span data-ttu-id="8aab1-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8aab1-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8aab1-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8aab1-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="8aab1-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8aab1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8aab1-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="8aab1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8aab1-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="8aab1-111">targets : 'T[]</span></span>

<span data-ttu-id="8aab1-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="8aab1-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8aab1-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8aab1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8aab1-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8aab1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8aab1-115">Nem</span><span class="sxs-lookup"><span data-stu-id="8aab1-115">'T</span></span>

<span data-ttu-id="8aab1-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="8aab1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8aab1-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8aab1-117">See Also</span></span>

- [<span data-ttu-id="8aab1-118">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="8aab1-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="8aab1-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="8aab1-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="8aab1-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="8aab1-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)