---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717672"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="cd3e5-102">ApplySeriesOfOps művelet</span><span class="sxs-lookup"><span data-stu-id="cd3e5-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="cd3e5-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cd3e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cd3e5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd3e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd3e5-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="cd3e5-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cd3e5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cd3e5-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="cd3e5-107">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="cd3e5-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="cd3e5-108">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="cd3e5-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="cd3e5-109">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="cd3e5-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="cd3e5-110">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="cd3e5-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="cd3e5-111">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="cd3e5-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="cd3e5-112">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="cd3e5-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="cd3e5-113">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="cd3e5-113">register : 'T[]</span></span>

<span data-ttu-id="cd3e5-114">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="cd3e5-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd3e5-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd3e5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cd3e5-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="cd3e5-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cd3e5-117">Nem</span><span class="sxs-lookup"><span data-stu-id="cd3e5-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="cd3e5-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="cd3e5-118">See Also</span></span>

- [<span data-ttu-id="cd3e5-119">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="cd3e5-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)