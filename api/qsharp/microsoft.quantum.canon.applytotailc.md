---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716972"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="e3bcf-102">ApplyToTailC művelet</span><span class="sxs-lookup"><span data-stu-id="e3bcf-102">ApplyToTailC operation</span></span>

<span data-ttu-id="e3bcf-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e3bcf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e3bcf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3bcf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3bcf-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="e3bcf-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e3bcf-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e3bcf-106">Description</span></span>

<span data-ttu-id="e3bcf-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e3bcf-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e3bcf-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e3bcf-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="e3bcf-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="e3bcf-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="e3bcf-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="e3bcf-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e3bcf-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="e3bcf-111">targets : 'T[]</span></span>

<span data-ttu-id="e3bcf-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="e3bcf-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3bcf-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3bcf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e3bcf-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e3bcf-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e3bcf-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e3bcf-115">'T</span></span>

<span data-ttu-id="e3bcf-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="e3bcf-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3bcf-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e3bcf-117">See Also</span></span>

- [<span data-ttu-id="e3bcf-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="e3bcf-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="e3bcf-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="e3bcf-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="e3bcf-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="e3bcf-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)