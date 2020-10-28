---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717084"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="f8ed2-102">ApplyToRestA művelet</span><span class="sxs-lookup"><span data-stu-id="f8ed2-102">ApplyToRestA operation</span></span>

<span data-ttu-id="f8ed2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f8ed2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f8ed2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8ed2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8ed2-105">A művelet a tömb első elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="f8ed2-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f8ed2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f8ed2-106">Description</span></span>

<span data-ttu-id="f8ed2-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f8ed2-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f8ed2-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f8ed2-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="f8ed2-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="f8ed2-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f8ed2-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="f8ed2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f8ed2-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="f8ed2-111">targets : 'T[]</span></span>

<span data-ttu-id="f8ed2-112">A célok tömbje, amelyből az összes, de az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="f8ed2-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8ed2-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8ed2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f8ed2-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f8ed2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8ed2-115">Nem</span><span class="sxs-lookup"><span data-stu-id="f8ed2-115">'T</span></span>

<span data-ttu-id="f8ed2-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="f8ed2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8ed2-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f8ed2-117">See Also</span></span>

- [<span data-ttu-id="f8ed2-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="f8ed2-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="f8ed2-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="f8ed2-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="f8ed2-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="f8ed2-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)