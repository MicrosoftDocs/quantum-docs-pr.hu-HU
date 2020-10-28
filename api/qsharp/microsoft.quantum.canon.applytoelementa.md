---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717490"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="0dd46-102">ApplyToElementA művelet</span><span class="sxs-lookup"><span data-stu-id="0dd46-102">ApplyToElementA operation</span></span>

<span data-ttu-id="0dd46-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0dd46-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0dd46-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0dd46-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0dd46-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="0dd46-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="0dd46-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="0dd46-106">Description</span></span>

<span data-ttu-id="0dd46-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="0dd46-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="0dd46-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0dd46-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="0dd46-109">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="0dd46-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="0dd46-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="0dd46-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="0dd46-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0dd46-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0dd46-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="0dd46-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="0dd46-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="0dd46-113">targets : 'T[]</span></span>

<span data-ttu-id="0dd46-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="0dd46-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0dd46-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0dd46-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0dd46-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="0dd46-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0dd46-117">Nem</span><span class="sxs-lookup"><span data-stu-id="0dd46-117">'T</span></span>

<span data-ttu-id="0dd46-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="0dd46-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dd46-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0dd46-119">See Also</span></span>

- [<span data-ttu-id="0dd46-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="0dd46-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="0dd46-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="0dd46-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="0dd46-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="0dd46-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)