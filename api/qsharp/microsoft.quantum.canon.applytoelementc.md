---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217577"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="98b5e-102">ApplyToElementC művelet</span><span class="sxs-lookup"><span data-stu-id="98b5e-102">ApplyToElementC operation</span></span>

<span data-ttu-id="98b5e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="98b5e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="98b5e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98b5e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98b5e-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="98b5e-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="98b5e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="98b5e-106">Description</span></span>

<span data-ttu-id="98b5e-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="98b5e-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="98b5e-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="98b5e-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="98b5e-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="98b5e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="98b5e-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="98b5e-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="98b5e-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98b5e-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98b5e-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="98b5e-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="98b5e-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="98b5e-113">targets : 'T[]</span></span>

<span data-ttu-id="98b5e-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="98b5e-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98b5e-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98b5e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="98b5e-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="98b5e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="98b5e-117">Nem</span><span class="sxs-lookup"><span data-stu-id="98b5e-117">'T</span></span>

<span data-ttu-id="98b5e-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="98b5e-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="98b5e-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="98b5e-119">See Also</span></span>

- [<span data-ttu-id="98b5e-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="98b5e-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="98b5e-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="98b5e-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="98b5e-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="98b5e-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)