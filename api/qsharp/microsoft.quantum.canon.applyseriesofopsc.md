---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: eaa0ea3e33cce708af5879cfbe875397fbb82a8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217934"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="4a6a0-102">ApplySeriesOfOpsC művelet</span><span class="sxs-lookup"><span data-stu-id="4a6a0-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="4a6a0-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a6a0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a6a0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a6a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a6a0-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="4a6a0-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="4a6a0-106">Ellenőrzött</span><span class="sxs-lookup"><span data-stu-id="4a6a0-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="4a6a0-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4a6a0-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="4a6a0-108">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL []</span><span class="sxs-lookup"><span data-stu-id="4a6a0-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="4a6a0-109">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="4a6a0-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="4a6a0-110">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="4a6a0-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="4a6a0-111">Mindegyiknek rendelkeznie kell egy vezérelt</span><span class="sxs-lookup"><span data-stu-id="4a6a0-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="4a6a0-112">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="4a6a0-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="4a6a0-113">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="4a6a0-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="4a6a0-114">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="4a6a0-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="4a6a0-115">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="4a6a0-115">register : 'T[]</span></span>

<span data-ttu-id="4a6a0-116">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="4a6a0-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a6a0-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a6a0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a6a0-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4a6a0-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a6a0-119">Nem</span><span class="sxs-lookup"><span data-stu-id="4a6a0-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="4a6a0-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4a6a0-120">See Also</span></span>

- [<span data-ttu-id="4a6a0-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="4a6a0-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)