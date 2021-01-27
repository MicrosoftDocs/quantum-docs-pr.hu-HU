---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850556"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="8b6f1-102">ApplyToMostC művelet</span><span class="sxs-lookup"><span data-stu-id="8b6f1-102">ApplyToMostC operation</span></span>

<span data-ttu-id="8b6f1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8b6f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8b6f1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b6f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b6f1-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="8b6f1-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8b6f1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8b6f1-106">Description</span></span>

<span data-ttu-id="8b6f1-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8b6f1-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8b6f1-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8b6f1-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8b6f1-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="8b6f1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8b6f1-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="8b6f1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8b6f1-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="8b6f1-111">targets : 'T[]</span></span>

<span data-ttu-id="8b6f1-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="8b6f1-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b6f1-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b6f1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8b6f1-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8b6f1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b6f1-115">Nem</span><span class="sxs-lookup"><span data-stu-id="8b6f1-115">'T</span></span>

<span data-ttu-id="8b6f1-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="8b6f1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b6f1-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8b6f1-117">See Also</span></span>

- [<span data-ttu-id="8b6f1-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="8b6f1-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="8b6f1-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="8b6f1-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="8b6f1-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="8b6f1-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)