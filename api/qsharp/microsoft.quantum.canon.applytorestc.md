---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850494"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="2b068-102">ApplyToRestC művelet</span><span class="sxs-lookup"><span data-stu-id="2b068-102">ApplyToRestC operation</span></span>

<span data-ttu-id="2b068-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b068-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b068-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b068-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b068-105">A művelet a tömb első elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="2b068-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="2b068-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2b068-106">Description</span></span>

<span data-ttu-id="2b068-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2b068-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2b068-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2b068-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="2b068-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="2b068-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2b068-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="2b068-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2b068-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="2b068-111">targets : 'T[]</span></span>

<span data-ttu-id="2b068-112">A célok tömbje, amelyből az összes, de az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="2b068-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b068-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b068-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2b068-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2b068-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b068-115">Nem</span><span class="sxs-lookup"><span data-stu-id="2b068-115">'T</span></span>

<span data-ttu-id="2b068-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2b068-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b068-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2b068-117">See Also</span></span>

- [<span data-ttu-id="2b068-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="2b068-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="2b068-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="2b068-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="2b068-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="2b068-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)