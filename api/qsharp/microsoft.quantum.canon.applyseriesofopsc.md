---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844652"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="f9719-102">ApplySeriesOfOpsC művelet</span><span class="sxs-lookup"><span data-stu-id="f9719-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="f9719-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f9719-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f9719-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9719-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9719-105">Egy tömbön egymás után az Ops és a célok listáját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="f9719-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="f9719-106">Ellenőrzött</span><span class="sxs-lookup"><span data-stu-id="f9719-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f9719-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f9719-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="f9719-108">listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL []</span><span class="sxs-lookup"><span data-stu-id="f9719-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="f9719-109">Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="f9719-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="f9719-110">A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.</span><span class="sxs-lookup"><span data-stu-id="f9719-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="f9719-111">Mindegyiknek rendelkeznie kell egy vezérelt</span><span class="sxs-lookup"><span data-stu-id="f9719-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="f9719-112">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="f9719-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="f9719-113">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="f9719-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="f9719-114">Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="f9719-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="f9719-115">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="f9719-115">register : 'T[]</span></span>

<span data-ttu-id="f9719-116">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="f9719-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9719-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9719-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9719-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f9719-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9719-119">Nem</span><span class="sxs-lookup"><span data-stu-id="f9719-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="f9719-120">Példa</span><span class="sxs-lookup"><span data-stu-id="f9719-120">Example</span></span>

<span data-ttu-id="f9719-121">A következők az exp ([PauliX, Pauliy], 0,5) értékre vonatkoznak, hogy qubits a 0, 1//, majd X qubit 2 let Ops = [exp ([PauliX, Pauliy], 0,5, _), ApplyToFirstQubitC (X, _)]; indexek kihagyhatása = [[0, 1], [2]]; ApplySeriesOfOpsC (Ops, indexek, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="f9719-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitC(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsC(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="f9719-122">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f9719-122">See Also</span></span>

- [<span data-ttu-id="f9719-123">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="f9719-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)