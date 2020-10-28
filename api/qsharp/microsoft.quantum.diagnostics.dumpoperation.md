---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712857"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="7a1da-102">DumpOperation művelet</span><span class="sxs-lookup"><span data-stu-id="7a1da-102">DumpOperation operation</span></span>

<span data-ttu-id="7a1da-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7a1da-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7a1da-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a1da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a1da-105">A művelet végrehajtásakor az aktuális végrehajtási cél által elérhetővé tett művelet diagnosztika jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7a1da-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="7a1da-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7a1da-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="7a1da-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a1da-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a1da-108">Azon qubits száma, amelyeken a megadott művelet működik.</span><span class="sxs-lookup"><span data-stu-id="7a1da-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit-adj"></a><span data-ttu-id="7a1da-109">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="7a1da-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7a1da-110">A diagnosztizálni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="7a1da-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a1da-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a1da-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7a1da-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7a1da-112">Remarks</span></span>

<span data-ttu-id="7a1da-113">A művelet meghívása nem befolyásolható a Q #-on belül.</span><span class="sxs-lookup"><span data-stu-id="7a1da-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="7a1da-114">Ha vannak ilyenek, a pontos diagnosztika az aktuális végrehajtási cél és a szerkesztő környezettől függ.</span><span class="sxs-lookup"><span data-stu-id="7a1da-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="7a1da-115">Ha például a teljes állapotú kvantum-szimulátort használja, megjelenik egy, a jelöléshez használt egységes mátrix `op` .</span><span class="sxs-lookup"><span data-stu-id="7a1da-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="7a1da-116">Vegye figyelembe, hogy ha olyan szimulátorokon fut, amelyek globális fázist (például a teljes állapotú szimulátort) fogadnak el, a visszaküldött adatábrázolások globális fázisban is változhatnak.</span><span class="sxs-lookup"><span data-stu-id="7a1da-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="7a1da-117">Hasonlóképpen, a sorok és oszlopok mátrix-ábrázolások sorrendje eltérő lehet a műveletet támogató egyes szimulátorok által használt konvenciókkal.</span><span class="sxs-lookup"><span data-stu-id="7a1da-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>