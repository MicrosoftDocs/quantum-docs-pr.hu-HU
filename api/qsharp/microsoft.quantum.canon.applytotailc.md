---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5a68cae3fd122416cfd064e0078e03f5c00ab492
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217288"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="2109c-102">ApplyToTailC művelet</span><span class="sxs-lookup"><span data-stu-id="2109c-102">ApplyToTailC operation</span></span>

<span data-ttu-id="2109c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2109c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2109c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2109c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2109c-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="2109c-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="2109c-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2109c-106">Description</span></span>

<span data-ttu-id="2109c-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2109c-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2109c-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2109c-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="2109c-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="2109c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2109c-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="2109c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2109c-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="2109c-111">targets : 'T[]</span></span>

<span data-ttu-id="2109c-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="2109c-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2109c-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2109c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2109c-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2109c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2109c-115">Nem</span><span class="sxs-lookup"><span data-stu-id="2109c-115">'T</span></span>

<span data-ttu-id="2109c-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2109c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2109c-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2109c-117">See Also</span></span>

- [<span data-ttu-id="2109c-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="2109c-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="2109c-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="2109c-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="2109c-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="2109c-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)