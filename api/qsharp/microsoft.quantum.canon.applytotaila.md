---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 2cacac14ad6e5003f1a50d9b84c4e0f96950dd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207921"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="e6ebc-102">ApplyToTailA művelet</span><span class="sxs-lookup"><span data-stu-id="e6ebc-102">ApplyToTailA operation</span></span>

<span data-ttu-id="e6ebc-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6ebc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6ebc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6ebc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6ebc-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="e6ebc-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="e6ebc-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e6ebc-106">Description</span></span>

<span data-ttu-id="e6ebc-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e6ebc-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e6ebc-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e6ebc-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="e6ebc-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6ebc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e6ebc-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="e6ebc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e6ebc-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="e6ebc-111">targets : 'T[]</span></span>

<span data-ttu-id="e6ebc-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="e6ebc-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6ebc-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6ebc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e6ebc-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e6ebc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6ebc-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e6ebc-115">'T</span></span>

<span data-ttu-id="e6ebc-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="e6ebc-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6ebc-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e6ebc-117">See Also</span></span>

- [<span data-ttu-id="e6ebc-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="e6ebc-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="e6ebc-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="e6ebc-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="e6ebc-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="e6ebc-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)