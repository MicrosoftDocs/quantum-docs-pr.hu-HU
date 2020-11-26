---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218002"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="1944c-102">ApplySeriesOfOps művelet</span><span class="sxs-lookup"><span data-stu-id="1944c-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="1944c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1944c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1944c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1944c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1944c-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="1944c-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1944c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1944c-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="1944c-107">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="1944c-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="1944c-108">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="1944c-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="1944c-109">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="1944c-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="1944c-110">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="1944c-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="1944c-111">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="1944c-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="1944c-112">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="1944c-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="1944c-113">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="1944c-113">register : 'T[]</span></span>

<span data-ttu-id="1944c-114">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="1944c-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1944c-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1944c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1944c-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1944c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1944c-117">Nem</span><span class="sxs-lookup"><span data-stu-id="1944c-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="1944c-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="1944c-118">See Also</span></span>

- [<span data-ttu-id="1944c-119">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="1944c-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)