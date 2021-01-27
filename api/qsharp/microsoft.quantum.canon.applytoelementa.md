---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850768"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="be105-102">ApplyToElementA művelet</span><span class="sxs-lookup"><span data-stu-id="be105-102">ApplyToElementA operation</span></span>

<span data-ttu-id="be105-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be105-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be105-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be105-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be105-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="be105-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="be105-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="be105-106">Description</span></span>

<span data-ttu-id="be105-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="be105-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="be105-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="be105-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="be105-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be105-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="be105-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="be105-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="be105-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be105-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be105-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="be105-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="be105-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="be105-113">targets : 'T[]</span></span>

<span data-ttu-id="be105-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="be105-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be105-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be105-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="be105-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="be105-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be105-117">Nem</span><span class="sxs-lookup"><span data-stu-id="be105-117">'T</span></span>

<span data-ttu-id="be105-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="be105-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="be105-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="be105-119">See Also</span></span>

- [<span data-ttu-id="be105-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="be105-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="be105-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="be105-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="be105-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="be105-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)