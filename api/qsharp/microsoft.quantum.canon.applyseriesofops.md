---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841501"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="2c5a8-102">ApplySeriesOfOps művelet</span><span class="sxs-lookup"><span data-stu-id="2c5a8-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="2c5a8-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c5a8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c5a8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c5a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c5a8-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="2c5a8-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2c5a8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2c5a8-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="2c5a8-107">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="2c5a8-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="2c5a8-108">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="2c5a8-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="2c5a8-109">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="2c5a8-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="2c5a8-110">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="2c5a8-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="2c5a8-111">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="2c5a8-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="2c5a8-112">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="2c5a8-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="2c5a8-113">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="2c5a8-113">register : 'T[]</span></span>

<span data-ttu-id="2c5a8-114">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="2c5a8-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c5a8-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c5a8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c5a8-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2c5a8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c5a8-117">Nem</span><span class="sxs-lookup"><span data-stu-id="2c5a8-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="2c5a8-118">Példa</span><span class="sxs-lookup"><span data-stu-id="2c5a8-118">Example</span></span>

<span data-ttu-id="2c5a8-119">A következők az exp ([PauliX, Pauliy], 0,5) értékre vonatkoznak, hogy qubits a 0, 1//, majd X qubit 2 let Ops = [exp ([PauliX, Pauliy], 0,5, _), ApplyToFirstQubit (X, _)]; indexek kihagyhatása = [[0, 1], [2]]; ApplySeriesOfOps (Ops, indexek, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="2c5a8-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="2c5a8-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2c5a8-120">See Also</span></span>

- [<span data-ttu-id="2c5a8-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="2c5a8-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)