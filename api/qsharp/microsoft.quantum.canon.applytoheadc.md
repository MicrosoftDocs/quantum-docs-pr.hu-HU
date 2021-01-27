---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850628"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="69928-102">ApplyToHeadC művelet</span><span class="sxs-lookup"><span data-stu-id="69928-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="69928-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69928-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69928-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69928-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69928-105">Egy műveletet alkalmaz egy tömb első elemére.</span><span class="sxs-lookup"><span data-stu-id="69928-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="69928-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="69928-106">Description</span></span>

<span data-ttu-id="69928-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="69928-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="69928-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="69928-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="69928-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="69928-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="69928-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="69928-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="69928-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="69928-111">targets : 'T[]</span></span>

<span data-ttu-id="69928-112">A célok tömbje, amelyből az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="69928-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69928-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69928-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="69928-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="69928-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69928-115">Nem</span><span class="sxs-lookup"><span data-stu-id="69928-115">'T</span></span>

<span data-ttu-id="69928-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="69928-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="69928-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="69928-117">See Also</span></span>

- [<span data-ttu-id="69928-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="69928-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="69928-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="69928-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="69928-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="69928-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)