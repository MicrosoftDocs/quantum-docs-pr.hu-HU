---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 420a92ae10d2fc260024968b1846e669c4b62d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841473"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="bc982-102">ApplyToElementCA művelet</span><span class="sxs-lookup"><span data-stu-id="bc982-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="bc982-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc982-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc982-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc982-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc982-105">Egy műveletet alkalmaz egy tömb egy adott elemére.</span><span class="sxs-lookup"><span data-stu-id="bc982-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="bc982-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="bc982-106">Description</span></span>

<span data-ttu-id="bc982-107">A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="bc982-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="bc982-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bc982-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="bc982-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="bc982-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bc982-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="bc982-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="bc982-111">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc982-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc982-112">Egy index a célok tömbje számára.</span><span class="sxs-lookup"><span data-stu-id="bc982-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="bc982-113">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="bc982-113">targets : 'T[]</span></span>

<span data-ttu-id="bc982-114">A lehetséges célpontok tömbje `op` .</span><span class="sxs-lookup"><span data-stu-id="bc982-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc982-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc982-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc982-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bc982-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc982-117">Nem</span><span class="sxs-lookup"><span data-stu-id="bc982-117">'T</span></span>

<span data-ttu-id="bc982-118">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="bc982-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc982-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bc982-119">See Also</span></span>

- [<span data-ttu-id="bc982-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="bc982-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="bc982-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="bc982-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="bc982-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="bc982-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)