---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717169"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="19fb2-102">ApplyToMostC művelet</span><span class="sxs-lookup"><span data-stu-id="19fb2-102">ApplyToMostC operation</span></span>

<span data-ttu-id="19fb2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="19fb2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="19fb2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19fb2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19fb2-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="19fb2-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="19fb2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="19fb2-106">Description</span></span>

<span data-ttu-id="19fb2-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="19fb2-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="19fb2-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="19fb2-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="19fb2-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="19fb2-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="19fb2-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="19fb2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="19fb2-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="19fb2-111">targets : 'T[]</span></span>

<span data-ttu-id="19fb2-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="19fb2-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19fb2-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19fb2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="19fb2-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="19fb2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="19fb2-115">Nem</span><span class="sxs-lookup"><span data-stu-id="19fb2-115">'T</span></span>

<span data-ttu-id="19fb2-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="19fb2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="19fb2-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="19fb2-117">See Also</span></span>

- [<span data-ttu-id="19fb2-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="19fb2-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="19fb2-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="19fb2-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="19fb2-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="19fb2-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)