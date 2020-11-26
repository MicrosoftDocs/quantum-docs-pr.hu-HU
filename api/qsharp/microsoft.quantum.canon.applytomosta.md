---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208499"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="b4128-102">ApplyToMostA művelet</span><span class="sxs-lookup"><span data-stu-id="b4128-102">ApplyToMostA operation</span></span>

<span data-ttu-id="b4128-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b4128-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b4128-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4128-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4128-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="b4128-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b4128-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b4128-106">Description</span></span>

<span data-ttu-id="b4128-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b4128-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b4128-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b4128-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="b4128-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4128-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b4128-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="b4128-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b4128-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="b4128-111">targets : 'T[]</span></span>

<span data-ttu-id="b4128-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="b4128-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4128-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4128-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b4128-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b4128-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b4128-115">Nem</span><span class="sxs-lookup"><span data-stu-id="b4128-115">'T</span></span>

<span data-ttu-id="b4128-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="b4128-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4128-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b4128-117">See Also</span></span>

- [<span data-ttu-id="b4128-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="b4128-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="b4128-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="b4128-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="b4128-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="b4128-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)