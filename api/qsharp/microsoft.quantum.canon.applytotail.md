---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207972"
---
# <a name="applytotail-operation"></a><span data-ttu-id="ebad2-102">ApplyToTail művelet</span><span class="sxs-lookup"><span data-stu-id="ebad2-102">ApplyToTail operation</span></span>

<span data-ttu-id="ebad2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ebad2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ebad2-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebad2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebad2-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="ebad2-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ebad2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ebad2-106">Description</span></span>

<span data-ttu-id="ebad2-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ebad2-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ebad2-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ebad2-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ebad2-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebad2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ebad2-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="ebad2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ebad2-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="ebad2-111">targets : 'T[]</span></span>

<span data-ttu-id="ebad2-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="ebad2-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebad2-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebad2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ebad2-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ebad2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ebad2-115">Nem</span><span class="sxs-lookup"><span data-stu-id="ebad2-115">'T</span></span>

<span data-ttu-id="ebad2-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="ebad2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebad2-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ebad2-117">See Also</span></span>

- [<span data-ttu-id="ebad2-118">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="ebad2-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="ebad2-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="ebad2-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="ebad2-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="ebad2-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)