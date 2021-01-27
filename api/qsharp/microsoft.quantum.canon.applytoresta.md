---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841271"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="f6600-102">ApplyToRestA művelet</span><span class="sxs-lookup"><span data-stu-id="f6600-102">ApplyToRestA operation</span></span>

<span data-ttu-id="f6600-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f6600-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f6600-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6600-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6600-105">A művelet a tömb első elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="f6600-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="f6600-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f6600-106">Description</span></span>

<span data-ttu-id="f6600-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f6600-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f6600-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f6600-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="f6600-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6600-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f6600-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="f6600-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f6600-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="f6600-111">targets : 'T[]</span></span>

<span data-ttu-id="f6600-112">A célok tömbje, amelyből az összes, de az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="f6600-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f6600-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f6600-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f6600-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f6600-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f6600-115">Nem</span><span class="sxs-lookup"><span data-stu-id="f6600-115">'T</span></span>

<span data-ttu-id="f6600-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="f6600-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6600-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f6600-117">See Also</span></span>

- [<span data-ttu-id="f6600-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="f6600-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="f6600-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="f6600-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="f6600-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="f6600-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)