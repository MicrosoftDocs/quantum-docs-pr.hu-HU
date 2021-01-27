---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: ApplyOpRepeatedlyOverC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 1cf3f32f0d25c1b4437f2bdbd93171a1a2e1e760
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844778"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="e2766-102">ApplyOpRepeatedlyOverC művelet</span><span class="sxs-lookup"><span data-stu-id="e2766-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="e2766-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2766-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2766-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2766-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2766-105">Ugyanazokat az op-ket alkalmazza a qubit-regisztrációnál többször.</span><span class="sxs-lookup"><span data-stu-id="e2766-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="e2766-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e2766-106">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="e2766-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="e2766-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e2766-108">A qubit-regisztráción többször alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="e2766-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="e2766-109">célok: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="e2766-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="e2766-110">Az op céljait leíró beágyazott tömbök.</span><span class="sxs-lookup"><span data-stu-id="e2766-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="e2766-111">Minden tömbnek tartalmaznia kell a használni kívánt qubits leíró csoportcsomagból listáját.</span><span class="sxs-lookup"><span data-stu-id="e2766-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e2766-112">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e2766-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e2766-113">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="e2766-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2766-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2766-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e2766-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e2766-115">See Also</span></span>

- [<span data-ttu-id="e2766-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="e2766-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)