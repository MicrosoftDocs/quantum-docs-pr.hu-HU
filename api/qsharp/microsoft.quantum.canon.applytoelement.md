---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717505"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="2b035-102">ApplyToElement művelet</span><span class="sxs-lookup"><span data-stu-id="2b035-102">ApplyToElement operation</span></span>

<span data-ttu-id="2b035-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b035-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b035-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b035-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b035-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="2b035-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="2b035-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2b035-106">Description</span></span>

<span data-ttu-id="2b035-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="2b035-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="2b035-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2b035-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="2b035-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b035-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2b035-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="2b035-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="2b035-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b035-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b035-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="2b035-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2b035-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="2b035-113">targets : 'T[]</span></span>

<span data-ttu-id="2b035-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="2b035-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b035-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b035-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2b035-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2b035-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b035-117">Nem</span><span class="sxs-lookup"><span data-stu-id="2b035-117">'T</span></span>

<span data-ttu-id="2b035-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2b035-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b035-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2b035-119">See Also</span></span>

- [<span data-ttu-id="2b035-120">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="2b035-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="2b035-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="2b035-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="2b035-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="2b035-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)