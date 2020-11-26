---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 3123c7f7b5e5c7f5cb17a34eedc81b3912109883
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208159"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="4cf29-102">ApplyToRestCA művelet</span><span class="sxs-lookup"><span data-stu-id="4cf29-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="4cf29-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4cf29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4cf29-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4cf29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4cf29-105">A művelet a tömb első elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="4cf29-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4cf29-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4cf29-106">Description</span></span>

<span data-ttu-id="4cf29-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4cf29-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4cf29-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4cf29-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="4cf29-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="4cf29-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4cf29-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="4cf29-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4cf29-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="4cf29-111">targets : 'T[]</span></span>

<span data-ttu-id="4cf29-112">A célok tömbje, amelyből az összes, de az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="4cf29-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4cf29-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cf29-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4cf29-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4cf29-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4cf29-115">Nem</span><span class="sxs-lookup"><span data-stu-id="4cf29-115">'T</span></span>

<span data-ttu-id="4cf29-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="4cf29-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cf29-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4cf29-117">See Also</span></span>

- [<span data-ttu-id="4cf29-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="4cf29-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="4cf29-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="4cf29-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="4cf29-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="4cf29-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)