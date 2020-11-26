---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208303"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="d6185-102">ApplyToRestA művelet</span><span class="sxs-lookup"><span data-stu-id="d6185-102">ApplyToRestA operation</span></span>

<span data-ttu-id="d6185-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d6185-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d6185-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6185-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6185-105">A művelet a tömb első elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="d6185-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="d6185-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d6185-106">Description</span></span>

<span data-ttu-id="d6185-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d6185-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d6185-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d6185-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="d6185-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6185-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d6185-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="d6185-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d6185-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="d6185-111">targets : 'T[]</span></span>

<span data-ttu-id="d6185-112">A célok tömbje, amelyből az összes, de az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="d6185-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6185-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6185-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d6185-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d6185-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d6185-115">Nem</span><span class="sxs-lookup"><span data-stu-id="d6185-115">'T</span></span>

<span data-ttu-id="d6185-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="d6185-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6185-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d6185-117">See Also</span></span>

- [<span data-ttu-id="d6185-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="d6185-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="d6185-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="d6185-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="d6185-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="d6185-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)