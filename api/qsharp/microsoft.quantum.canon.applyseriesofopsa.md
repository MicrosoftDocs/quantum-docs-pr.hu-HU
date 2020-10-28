---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717658"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="fcfab-102">ApplySeriesOfOpsA művelet</span><span class="sxs-lookup"><span data-stu-id="fcfab-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="fcfab-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fcfab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fcfab-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcfab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcfab-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="fcfab-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="fcfab-106">(Adjoint)</span><span class="sxs-lookup"><span data-stu-id="fcfab-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fcfab-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fcfab-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="fcfab-108">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj []</span><span class="sxs-lookup"><span data-stu-id="fcfab-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="fcfab-109">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="fcfab-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="fcfab-110">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="fcfab-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="fcfab-111">Mindegyiknek rendelkeznie kell egy adjoint-bejelentkezővel</span><span class="sxs-lookup"><span data-stu-id="fcfab-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="fcfab-112">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="fcfab-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="fcfab-113">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="fcfab-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="fcfab-114">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="fcfab-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="fcfab-115">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="fcfab-115">register : 'T[]</span></span>

<span data-ttu-id="fcfab-116">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="fcfab-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcfab-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcfab-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fcfab-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="fcfab-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fcfab-119">Nem</span><span class="sxs-lookup"><span data-stu-id="fcfab-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="fcfab-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fcfab-120">See Also</span></span>

- [<span data-ttu-id="fcfab-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="fcfab-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)