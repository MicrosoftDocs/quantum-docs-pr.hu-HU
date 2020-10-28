---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 994cada2952809dc84a70b76dc4ede8286c89855
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717210"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="6bf41-102">ApplyToMostA művelet</span><span class="sxs-lookup"><span data-stu-id="6bf41-102">ApplyToMostA operation</span></span>

<span data-ttu-id="6bf41-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6bf41-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6bf41-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6bf41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6bf41-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="6bf41-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6bf41-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6bf41-106">Description</span></span>

<span data-ttu-id="6bf41-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6bf41-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6bf41-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6bf41-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="6bf41-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="6bf41-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6bf41-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="6bf41-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6bf41-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="6bf41-111">targets : 'T[]</span></span>

<span data-ttu-id="6bf41-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="6bf41-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bf41-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bf41-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6bf41-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6bf41-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6bf41-115">Nem</span><span class="sxs-lookup"><span data-stu-id="6bf41-115">'T</span></span>

<span data-ttu-id="6bf41-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6bf41-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bf41-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6bf41-117">See Also</span></span>

- [<span data-ttu-id="6bf41-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="6bf41-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="6bf41-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="6bf41-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="6bf41-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="6bf41-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)