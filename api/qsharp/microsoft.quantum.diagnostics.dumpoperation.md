---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202056"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="aa3ad-102">DumpOperation művelet</span><span class="sxs-lookup"><span data-stu-id="aa3ad-102">DumpOperation operation</span></span>

<span data-ttu-id="aa3ad-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="aa3ad-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="aa3ad-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa3ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa3ad-105">A művelet végrehajtásakor az aktuális végrehajtási cél által elérhetővé tett művelet diagnosztika jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="aa3ad-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="aa3ad-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="aa3ad-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="aa3ad-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa3ad-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa3ad-108">Azon qubits száma, amelyeken a megadott művelet működik.</span><span class="sxs-lookup"><span data-stu-id="aa3ad-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="aa3ad-109">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa3ad-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="aa3ad-110">A diagnosztizálni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="aa3ad-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa3ad-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa3ad-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aa3ad-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="aa3ad-112">Remarks</span></span>

<span data-ttu-id="aa3ad-113">A művelet meghívása nem befolyásolható a Q #-on belül.</span><span class="sxs-lookup"><span data-stu-id="aa3ad-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="aa3ad-114">Ha vannak ilyenek, a pontos diagnosztika az aktuális végrehajtási cél és a szerkesztő környezettől függ.</span><span class="sxs-lookup"><span data-stu-id="aa3ad-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="aa3ad-115">Ha például a teljes állapotú kvantum-szimulátort használja, megjelenik egy, a jelöléshez használt egységes mátrix `op` .</span><span class="sxs-lookup"><span data-stu-id="aa3ad-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="aa3ad-116">Vegye figyelembe, hogy ha olyan szimulátorokon fut, amelyek globális fázist (például a teljes állapotú szimulátort) fogadnak el, a visszaküldött adatábrázolások globális fázisban is változhatnak.</span><span class="sxs-lookup"><span data-stu-id="aa3ad-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="aa3ad-117">Hasonlóképpen, a sorok és oszlopok mátrix-ábrázolások sorrendje eltérő lehet a műveletet támogató egyes szimulátorok által használt konvenciókkal.</span><span class="sxs-lookup"><span data-stu-id="aa3ad-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>