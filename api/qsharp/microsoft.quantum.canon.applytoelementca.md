---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208856"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="56b34-102">ApplyToElementCA művelet</span><span class="sxs-lookup"><span data-stu-id="56b34-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="56b34-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56b34-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56b34-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56b34-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56b34-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="56b34-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="56b34-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="56b34-106">Description</span></span>

<span data-ttu-id="56b34-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="56b34-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="56b34-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="56b34-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="56b34-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="56b34-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="56b34-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="56b34-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="56b34-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56b34-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="56b34-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="56b34-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="56b34-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="56b34-113">targets : 'T[]</span></span>

<span data-ttu-id="56b34-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="56b34-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56b34-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56b34-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="56b34-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="56b34-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56b34-117">Nem</span><span class="sxs-lookup"><span data-stu-id="56b34-117">'T</span></span>

<span data-ttu-id="56b34-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="56b34-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="56b34-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="56b34-119">See Also</span></span>

- [<span data-ttu-id="56b34-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="56b34-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="56b34-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="56b34-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="56b34-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="56b34-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)