---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724004"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="c170b-102">PrepareChoiState művelet</span><span class="sxs-lookup"><span data-stu-id="c170b-102">PrepareChoiState operation</span></span>

<span data-ttu-id="c170b-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c170b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c170b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c170b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c170b-105">Előkészíti a Choi – Jamiłkowski állapotot egy adott művelethez az adott referenciára és a cél-regisztrációra.</span><span class="sxs-lookup"><span data-stu-id="c170b-105">Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c170b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c170b-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="c170b-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c170b-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c170b-108">A $ \Lambda $, amelynek Choi-Jamiłkowski State $J (\Lambda)/2 ^ N $ értéket elő kell készíteni, ahol a $N $ érték azon qubits száma, amelyeken a művelet `op` működik.</span><span class="sxs-lookup"><span data-stu-id="c170b-108">Operation $\Lambda$ whose Choi–Jamiłkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="c170b-109">hivatkozás: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c170b-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c170b-110">A $ \ket{00\cdots 0} $ állapottól kezdődő qubits-regisztráció a műveletre mutató hivatkozásként való használatra `op` .</span><span class="sxs-lookup"><span data-stu-id="c170b-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c170b-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c170b-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c170b-112">A qubits-regisztráció kezdetben a $ \ket{00\cdots 0} $ állapotban van, amelyre `op` alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="c170b-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c170b-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c170b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c170b-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c170b-114">Remarks</span></span>

<span data-ttu-id="c170b-115">A Jamiłkowski State $J (\Lambda) $ of a kvantum-folyamat értéke $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $, ahol $ | A X\rangle \! \rangle $ egy mátrix $X $ *vektorizációt* az oszlop-halmozási konvencióban.</span><span class="sxs-lookup"><span data-stu-id="c170b-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="c170b-116">Az állapot klasszikus leírásának megismerése teljes körű információt nyújt a $ \Lambda $ működéséről, amely tetszőleges bemeneti állapotokra támaszkodik, és a *Quantum Process tomográfia* alapját képezi.</span><span class="sxs-lookup"><span data-stu-id="c170b-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography* .</span></span>

## <a name="see-also"></a><span data-ttu-id="c170b-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c170b-117">See Also</span></span>

- [<span data-ttu-id="c170b-118">Microsoft. Quantum. előkészítés. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="c170b-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="c170b-119">Microsoft. Quantum. előkészítés. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="c170b-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="c170b-120">Microsoft. Quantum. előkészítés. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="c170b-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)