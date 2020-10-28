---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717449"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="7e5e0-102">ApplyToElementC művelet</span><span class="sxs-lookup"><span data-stu-id="7e5e0-102">ApplyToElementC operation</span></span>

<span data-ttu-id="7e5e0-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e5e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e5e0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e5e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e5e0-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="7e5e0-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="7e5e0-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="7e5e0-106">Description</span></span>

<span data-ttu-id="7e5e0-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="7e5e0-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="7e5e0-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7e5e0-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="7e5e0-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7e5e0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7e5e0-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="7e5e0-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="7e5e0-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e5e0-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e5e0-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="7e5e0-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="7e5e0-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="7e5e0-113">targets : 'T[]</span></span>

<span data-ttu-id="7e5e0-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="7e5e0-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e5e0-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e5e0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7e5e0-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7e5e0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e5e0-117">Nem</span><span class="sxs-lookup"><span data-stu-id="7e5e0-117">'T</span></span>

<span data-ttu-id="7e5e0-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="7e5e0-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e5e0-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7e5e0-119">See Also</span></span>

- [<span data-ttu-id="7e5e0-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="7e5e0-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="7e5e0-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="7e5e0-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="7e5e0-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="7e5e0-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)