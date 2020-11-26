---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: af55093e44ce023c9e8b7e478730f4c527cf6d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208465"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="6ba1a-102">ApplyToMostC művelet</span><span class="sxs-lookup"><span data-stu-id="6ba1a-102">ApplyToMostC operation</span></span>

<span data-ttu-id="6ba1a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ba1a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ba1a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ba1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ba1a-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="6ba1a-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="6ba1a-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6ba1a-106">Description</span></span>

<span data-ttu-id="6ba1a-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6ba1a-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6ba1a-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6ba1a-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="6ba1a-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="6ba1a-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6ba1a-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="6ba1a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6ba1a-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="6ba1a-111">targets : 'T[]</span></span>

<span data-ttu-id="6ba1a-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="6ba1a-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ba1a-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ba1a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6ba1a-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6ba1a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ba1a-115">Nem</span><span class="sxs-lookup"><span data-stu-id="6ba1a-115">'T</span></span>

<span data-ttu-id="6ba1a-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6ba1a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ba1a-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6ba1a-117">See Also</span></span>

- [<span data-ttu-id="6ba1a-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="6ba1a-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="6ba1a-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="6ba1a-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="6ba1a-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="6ba1a-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)