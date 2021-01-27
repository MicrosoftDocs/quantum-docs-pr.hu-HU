---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854403"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="73ac3-102">PrepareChoiState művelet</span><span class="sxs-lookup"><span data-stu-id="73ac3-102">PrepareChoiState operation</span></span>

<span data-ttu-id="73ac3-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="73ac3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="73ac3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73ac3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73ac3-105">Előkészíti a Choi – Jamiołkowski állapotot egy adott művelethez az adott referenciára és a cél-regisztrációra.</span><span class="sxs-lookup"><span data-stu-id="73ac3-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="73ac3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="73ac3-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="73ac3-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73ac3-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="73ac3-108">A $ \Lambda $, amelynek Choi-Jamiołkowski State $J (\Lambda)/2 ^ N $ értéket elő kell készíteni, ahol a $N $ érték azon qubits száma, amelyeken a művelet `op` működik.</span><span class="sxs-lookup"><span data-stu-id="73ac3-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="73ac3-109">hivatkozás: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73ac3-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73ac3-110">A $ \ket{00\cdots 0} $ állapottól kezdődő qubits-regisztráció a műveletre mutató hivatkozásként való használatra `op` .</span><span class="sxs-lookup"><span data-stu-id="73ac3-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="73ac3-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73ac3-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73ac3-112">A qubits-regisztráció kezdetben a $ \ket{00\cdots 0} $ állapotban van, amelyre `op` alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="73ac3-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73ac3-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73ac3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="73ac3-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="73ac3-114">Remarks</span></span>

<span data-ttu-id="73ac3-115">A Jamiłkowski State $J (\Lambda) $ of a kvantum-folyamat értéke $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $, ahol $ | A X\rangle \! \rangle $ egy mátrix $X $ *vektorizációt* az oszlop-halmozási konvencióban.</span><span class="sxs-lookup"><span data-stu-id="73ac3-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="73ac3-116">Az állapot klasszikus leírásának megismerése teljes körű információt nyújt a $ \Lambda $ működéséről, amely tetszőleges bemeneti állapotokra támaszkodik, és a *Quantum Process tomográfia* alapját képezi.</span><span class="sxs-lookup"><span data-stu-id="73ac3-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="73ac3-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="73ac3-117">See Also</span></span>

- [<span data-ttu-id="73ac3-118">Microsoft. Quantum. előkészítés. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="73ac3-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="73ac3-119">Microsoft. Quantum. előkészítés. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="73ac3-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="73ac3-120">Microsoft. Quantum. előkészítés. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="73ac3-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)