---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: ApplyOpRepeatedlyOver művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 09f54be33a7b5c58a317a949290f5cd6d54fe841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717854"
---
# <a name="applyoprepeatedlyover-operation"></a><span data-ttu-id="8fdc4-102">ApplyOpRepeatedlyOver művelet</span><span class="sxs-lookup"><span data-stu-id="8fdc4-102">ApplyOpRepeatedlyOver operation</span></span>

<span data-ttu-id="8fdc4-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8fdc4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8fdc4-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8fdc4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8fdc4-105">Ugyanazokat az op-ket alkalmazza a qubit-regisztrációnál többször.</span><span class="sxs-lookup"><span data-stu-id="8fdc4-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8fdc4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8fdc4-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="8fdc4-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8fdc4-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8fdc4-108">A qubit-regisztráción többször alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="8fdc4-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="8fdc4-109">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="8fdc4-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="8fdc4-110">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="8fdc4-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="8fdc4-111">Minden tömbnek tartalmaznia kell a használni kívánt qubits leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="8fdc4-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="8fdc4-112">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8fdc4-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8fdc4-113">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="8fdc4-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8fdc4-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8fdc4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8fdc4-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8fdc4-115">See Also</span></span>

- [<span data-ttu-id="8fdc4-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="8fdc4-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)