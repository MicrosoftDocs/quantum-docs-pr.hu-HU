---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841312"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="2f8d7-102">ApplyToMostCA művelet</span><span class="sxs-lookup"><span data-stu-id="2f8d7-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="2f8d7-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f8d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f8d7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f8d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f8d7-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2f8d7-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2f8d7-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2f8d7-106">Description</span></span>

<span data-ttu-id="2f8d7-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2f8d7-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2f8d7-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2f8d7-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="2f8d7-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2f8d7-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2f8d7-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="2f8d7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2f8d7-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="2f8d7-111">targets : 'T[]</span></span>

<span data-ttu-id="2f8d7-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="2f8d7-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f8d7-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f8d7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f8d7-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2f8d7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f8d7-115">Nem</span><span class="sxs-lookup"><span data-stu-id="2f8d7-115">'T</span></span>

<span data-ttu-id="2f8d7-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2f8d7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f8d7-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2f8d7-117">See Also</span></span>

- [<span data-ttu-id="2f8d7-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="2f8d7-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="2f8d7-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="2f8d7-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="2f8d7-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="2f8d7-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)