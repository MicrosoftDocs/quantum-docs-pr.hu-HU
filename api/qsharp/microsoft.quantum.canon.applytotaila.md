---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841175"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="3638e-102">ApplyToTailA művelet</span><span class="sxs-lookup"><span data-stu-id="3638e-102">ApplyToTailA operation</span></span>

<span data-ttu-id="3638e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3638e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3638e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3638e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3638e-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="3638e-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="3638e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="3638e-106">Description</span></span>

<span data-ttu-id="3638e-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="3638e-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="3638e-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3638e-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="3638e-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3638e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3638e-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="3638e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="3638e-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="3638e-111">targets : 'T[]</span></span>

<span data-ttu-id="3638e-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="3638e-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3638e-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3638e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3638e-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3638e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3638e-115">Nem</span><span class="sxs-lookup"><span data-stu-id="3638e-115">'T</span></span>

<span data-ttu-id="3638e-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="3638e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3638e-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3638e-117">See Also</span></span>

- [<span data-ttu-id="3638e-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="3638e-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="3638e-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="3638e-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="3638e-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="3638e-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)