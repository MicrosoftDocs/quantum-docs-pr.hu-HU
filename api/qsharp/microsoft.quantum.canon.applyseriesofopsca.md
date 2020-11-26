---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217883"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="56ad6-102">ApplySeriesOfOpsCA művelet</span><span class="sxs-lookup"><span data-stu-id="56ad6-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="56ad6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56ad6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56ad6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56ad6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56ad6-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="56ad6-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="56ad6-106">(Adjoint + vezérelt)</span><span class="sxs-lookup"><span data-stu-id="56ad6-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="56ad6-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="56ad6-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="56ad6-108">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="56ad6-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="56ad6-109">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="56ad6-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="56ad6-110">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="56ad6-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="56ad6-111">Mindegyiknek rendelkeznie kell egy Adjoint és egy ellenőrzött felállóval.</span><span class="sxs-lookup"><span data-stu-id="56ad6-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="56ad6-112">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="56ad6-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="56ad6-113">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="56ad6-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="56ad6-114">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="56ad6-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="56ad6-115">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="56ad6-115">register : 'T[]</span></span>

<span data-ttu-id="56ad6-116">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="56ad6-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56ad6-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56ad6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="56ad6-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="56ad6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56ad6-119">Nem</span><span class="sxs-lookup"><span data-stu-id="56ad6-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="56ad6-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="56ad6-120">See Also</span></span>

- [<span data-ttu-id="56ad6-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="56ad6-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)