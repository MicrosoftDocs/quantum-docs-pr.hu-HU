---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841338"
---
# <a name="applytohead-operation"></a><span data-ttu-id="e2998-102">ApplyToHead művelet</span><span class="sxs-lookup"><span data-stu-id="e2998-102">ApplyToHead operation</span></span>

<span data-ttu-id="e2998-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2998-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2998-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2998-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2998-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="e2998-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e2998-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e2998-106">Description</span></span>

<span data-ttu-id="e2998-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e2998-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e2998-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e2998-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e2998-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2998-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e2998-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="e2998-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e2998-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="e2998-111">targets : 'T[]</span></span>

<span data-ttu-id="e2998-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="e2998-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2998-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2998-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e2998-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e2998-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e2998-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e2998-115">'T</span></span>

<span data-ttu-id="e2998-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="e2998-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="e2998-117">Példa</span><span class="sxs-lookup"><span data-stu-id="e2998-117">Example</span></span>

<span data-ttu-id="e2998-118">A következő Q # kódrészletek egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="e2998-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="e2998-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e2998-119">See Also</span></span>

- [<span data-ttu-id="e2998-120">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="e2998-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="e2998-121">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="e2998-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="e2998-122">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="e2998-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)