---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844664"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="76d71-102">ApplySeriesOfOpsA művelet</span><span class="sxs-lookup"><span data-stu-id="76d71-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="76d71-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="76d71-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="76d71-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76d71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76d71-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="76d71-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="76d71-106">(Adjoint)</span><span class="sxs-lookup"><span data-stu-id="76d71-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="76d71-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="76d71-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="76d71-108">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  []</span><span class="sxs-lookup"><span data-stu-id="76d71-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="76d71-109">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="76d71-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="76d71-110">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="76d71-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="76d71-111">Mindegyiknek rendelkeznie kell egy adjoint-bejelentkezővel</span><span class="sxs-lookup"><span data-stu-id="76d71-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="76d71-112">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="76d71-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="76d71-113">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="76d71-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="76d71-114">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="76d71-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="76d71-115">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="76d71-115">register : 'T[]</span></span>

<span data-ttu-id="76d71-116">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="76d71-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76d71-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76d71-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="76d71-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="76d71-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76d71-119">Nem</span><span class="sxs-lookup"><span data-stu-id="76d71-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="76d71-120">Példa</span><span class="sxs-lookup"><span data-stu-id="76d71-120">Example</span></span>

<span data-ttu-id="76d71-121">A következők az exp ([PauliX, Pauliy], 0,5) értékre vonatkoznak, hogy qubits a 0, 1//, majd X qubit 2 let Ops = [exp ([PauliX, Pauliy], 0,5, _), ApplyToFirstQubitA (X, _)]; indexek kihagyhatása = [[0, 1], [2]]; ApplySeriesOfOpsA (Ops, indexek, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="76d71-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="76d71-122">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="76d71-122">See Also</span></span>

- [<span data-ttu-id="76d71-123">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="76d71-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)