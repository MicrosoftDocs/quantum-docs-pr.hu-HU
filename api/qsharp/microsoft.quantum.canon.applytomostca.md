---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208414"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="e3a58-102">ApplyToMostCA művelet</span><span class="sxs-lookup"><span data-stu-id="e3a58-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="e3a58-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e3a58-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e3a58-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3a58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3a58-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="e3a58-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e3a58-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e3a58-106">Description</span></span>

<span data-ttu-id="e3a58-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e3a58-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e3a58-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e3a58-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="e3a58-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="e3a58-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e3a58-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="e3a58-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e3a58-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="e3a58-111">targets : 'T[]</span></span>

<span data-ttu-id="e3a58-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="e3a58-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3a58-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3a58-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e3a58-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e3a58-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e3a58-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e3a58-115">'T</span></span>

<span data-ttu-id="e3a58-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="e3a58-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3a58-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e3a58-117">See Also</span></span>

- [<span data-ttu-id="e3a58-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="e3a58-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="e3a58-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="e3a58-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="e3a58-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="e3a58-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)