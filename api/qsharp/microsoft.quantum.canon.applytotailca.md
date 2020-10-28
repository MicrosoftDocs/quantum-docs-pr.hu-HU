---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 00755df80981a09ddfd8327ee9b35761d30af4f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716944"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="5a0e4-102">ApplyToTailCA művelet</span><span class="sxs-lookup"><span data-stu-id="5a0e4-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="5a0e4-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a0e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a0e4-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a0e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a0e4-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="5a0e4-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="5a0e4-106">Description</span></span>

<span data-ttu-id="5a0e4-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="5a0e4-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="5a0e4-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5a0e4-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="5a0e4-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="5a0e4-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5a0e4-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="5a0e4-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="5a0e4-111">targets : 'T[]</span></span>

<span data-ttu-id="5a0e4-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="5a0e4-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a0e4-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a0e4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5a0e4-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="5a0e4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a0e4-115">Nem</span><span class="sxs-lookup"><span data-stu-id="5a0e4-115">'T</span></span>

<span data-ttu-id="5a0e4-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a0e4-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="5a0e4-117">See Also</span></span>

- [<span data-ttu-id="5a0e4-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="5a0e4-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="5a0e4-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="5a0e4-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="5a0e4-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="5a0e4-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)