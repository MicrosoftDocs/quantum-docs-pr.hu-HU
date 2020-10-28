---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717631"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="317bd-102">ApplySeriesOfOpsCA művelet</span><span class="sxs-lookup"><span data-stu-id="317bd-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="317bd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="317bd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="317bd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="317bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="317bd-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="317bd-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="317bd-106">(Adjoint + vezérelt)</span><span class="sxs-lookup"><span data-stu-id="317bd-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="317bd-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="317bd-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="317bd-108">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="317bd-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="317bd-109">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="317bd-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="317bd-110">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="317bd-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="317bd-111">Mindegyiknek rendelkeznie kell egy Adjoint és egy ellenőrzött felállóval.</span><span class="sxs-lookup"><span data-stu-id="317bd-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="317bd-112">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="317bd-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="317bd-113">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="317bd-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="317bd-114">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="317bd-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="317bd-115">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="317bd-115">register : 'T[]</span></span>

<span data-ttu-id="317bd-116">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="317bd-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="317bd-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="317bd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="317bd-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="317bd-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="317bd-119">Nem</span><span class="sxs-lookup"><span data-stu-id="317bd-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="317bd-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="317bd-120">See Also</span></span>

- [<span data-ttu-id="317bd-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="317bd-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)