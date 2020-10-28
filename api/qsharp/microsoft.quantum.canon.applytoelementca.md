---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717448"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="2ea82-102">ApplyToElementCA művelet</span><span class="sxs-lookup"><span data-stu-id="2ea82-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="2ea82-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2ea82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2ea82-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ea82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ea82-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="2ea82-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="2ea82-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2ea82-106">Description</span></span>

<span data-ttu-id="2ea82-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="2ea82-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="2ea82-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2ea82-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="2ea82-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2ea82-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2ea82-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="2ea82-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="2ea82-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ea82-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2ea82-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="2ea82-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2ea82-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="2ea82-113">targets : 'T[]</span></span>

<span data-ttu-id="2ea82-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="2ea82-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ea82-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ea82-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2ea82-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2ea82-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2ea82-117">Nem</span><span class="sxs-lookup"><span data-stu-id="2ea82-117">'T</span></span>

<span data-ttu-id="2ea82-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2ea82-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ea82-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2ea82-119">See Also</span></span>

- [<span data-ttu-id="2ea82-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="2ea82-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="2ea82-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="2ea82-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="2ea82-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="2ea82-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)