---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8cbc42a1c43b4c9a037729671eb3c82d365af580
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217627"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="130c1-102">ApplyToElement művelet</span><span class="sxs-lookup"><span data-stu-id="130c1-102">ApplyToElement operation</span></span>

<span data-ttu-id="130c1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="130c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="130c1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="130c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="130c1-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="130c1-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="130c1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="130c1-106">Description</span></span>

<span data-ttu-id="130c1-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="130c1-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="130c1-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="130c1-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="130c1-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="130c1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="130c1-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="130c1-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="130c1-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="130c1-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="130c1-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="130c1-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="130c1-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="130c1-113">targets : 'T[]</span></span>

<span data-ttu-id="130c1-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="130c1-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="130c1-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="130c1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="130c1-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="130c1-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="130c1-117">Nem</span><span class="sxs-lookup"><span data-stu-id="130c1-117">'T</span></span>

<span data-ttu-id="130c1-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="130c1-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="130c1-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="130c1-119">See Also</span></span>

- [<span data-ttu-id="130c1-120">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="130c1-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="130c1-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="130c1-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="130c1-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="130c1-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)