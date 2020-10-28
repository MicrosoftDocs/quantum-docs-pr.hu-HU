---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716973"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="43507-102">ApplyToTailA művelet</span><span class="sxs-lookup"><span data-stu-id="43507-102">ApplyToTailA operation</span></span>

<span data-ttu-id="43507-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="43507-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="43507-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43507-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43507-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="43507-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="43507-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="43507-106">Description</span></span>

<span data-ttu-id="43507-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="43507-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="43507-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="43507-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="43507-109">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="43507-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="43507-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="43507-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="43507-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="43507-111">targets : 'T[]</span></span>

<span data-ttu-id="43507-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="43507-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="43507-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43507-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="43507-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="43507-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43507-115">Nem</span><span class="sxs-lookup"><span data-stu-id="43507-115">'T</span></span>

<span data-ttu-id="43507-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="43507-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="43507-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="43507-117">See Also</span></span>

- [<span data-ttu-id="43507-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="43507-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="43507-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="43507-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="43507-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="43507-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)