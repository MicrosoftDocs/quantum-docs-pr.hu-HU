---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829275"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="a2455-102">DumpOperation művelet</span><span class="sxs-lookup"><span data-stu-id="a2455-102">DumpOperation operation</span></span>

<span data-ttu-id="a2455-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a2455-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a2455-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2455-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2455-105">A művelet végrehajtásakor az aktuális végrehajtási cél által elérhetővé tett művelet diagnosztika jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a2455-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="a2455-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a2455-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="a2455-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a2455-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a2455-108">Azon qubits száma, amelyeken a megadott művelet működik.</span><span class="sxs-lookup"><span data-stu-id="a2455-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="a2455-109">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2455-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a2455-110">A diagnosztizálni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="a2455-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2455-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2455-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="a2455-112">Példa</span><span class="sxs-lookup"><span data-stu-id="a2455-112">Example</span></span>

<span data-ttu-id="a2455-113">A kvantum-szimulátor célján való futtatáskor a következő kódrészlet kimenetet küld a Matrix $ $ \begin{aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{aligned}.</span><span class="sxs-lookup"><span data-stu-id="a2455-113">When run on the quantum simulator target, the following snippet will output the matrix $$ \begin{aligned} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}.</span></span>
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a><span data-ttu-id="a2455-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a2455-114">Remarks</span></span>

<span data-ttu-id="a2455-115">A művelet meghívása nem befolyásolható a Q #-on belül.</span><span class="sxs-lookup"><span data-stu-id="a2455-115">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="a2455-116">Ha vannak ilyenek, a pontos diagnosztika az aktuális végrehajtási cél és a szerkesztő környezettől függ.</span><span class="sxs-lookup"><span data-stu-id="a2455-116">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="a2455-117">Ha például a teljes állapotú kvantum-szimulátort használja, megjelenik egy, a jelöléshez használt egységes mátrix `op` .</span><span class="sxs-lookup"><span data-stu-id="a2455-117">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="a2455-118">Vegye figyelembe, hogy ha olyan szimulátorokon fut, amelyek globális fázist (például a teljes állapotú szimulátort) fogadnak el, a visszaküldött adatábrázolások globális fázisban is változhatnak.</span><span class="sxs-lookup"><span data-stu-id="a2455-118">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="a2455-119">Hasonlóképpen, a sorok és oszlopok mátrix-ábrázolások sorrendje eltérő lehet a műveletet támogató egyes szimulátorok által használt konvenciókkal.</span><span class="sxs-lookup"><span data-stu-id="a2455-119">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>