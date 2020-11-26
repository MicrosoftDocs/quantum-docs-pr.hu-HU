---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7e7824b431ccff644cf5cc53145163327eb8ad36
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208533"
---
# <a name="applytomost-operation"></a><span data-ttu-id="d15dd-102">ApplyToMost művelet</span><span class="sxs-lookup"><span data-stu-id="d15dd-102">ApplyToMost operation</span></span>

<span data-ttu-id="d15dd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d15dd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d15dd-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d15dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d15dd-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d15dd-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d15dd-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d15dd-106">Description</span></span>

<span data-ttu-id="d15dd-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d15dd-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d15dd-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d15dd-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d15dd-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d15dd-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d15dd-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="d15dd-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d15dd-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="d15dd-111">targets : 'T[]</span></span>

<span data-ttu-id="d15dd-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="d15dd-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d15dd-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d15dd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d15dd-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d15dd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d15dd-115">Nem</span><span class="sxs-lookup"><span data-stu-id="d15dd-115">'T</span></span>

<span data-ttu-id="d15dd-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="d15dd-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d15dd-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d15dd-117">See Also</span></span>

- [<span data-ttu-id="d15dd-118">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="d15dd-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="d15dd-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="d15dd-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="d15dd-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="d15dd-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)