---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851801"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="e875e-102">RobustPhaseEstimation művelet</span><span class="sxs-lookup"><span data-stu-id="e875e-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="e875e-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="e875e-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="e875e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e875e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e875e-105">Elvégzi a robusztus, nem ismétlődő kvantum-értékelési algoritmust egy adott Oracle `U` -és eigenstate esetében, és egyetlen valós értékű becslést nyújt a fázisról a Heisenberg korláton belüli variancia-méretezéssel.</span><span class="sxs-lookup"><span data-stu-id="e875e-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="e875e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e875e-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="e875e-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e875e-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e875e-108">Ez becslést ad a $ \phi $-re a standard szintű szórással ($ \sigma \Le 2 \ pi/2 ^ \text{bitsPrecision} $) a több lekérdezéssel, például a $ \sigma \Le 10,7 \pi/\text{# of kérdezgető} $ méretezéssel.</span><span class="sxs-lookup"><span data-stu-id="e875e-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="e875e-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="e875e-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="e875e-110">Egy művelet, amely $U ^ millió $ értéket implementál a megadott egész számra $m $.</span><span class="sxs-lookup"><span data-stu-id="e875e-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="e875e-111">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e875e-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e875e-112">Egy kvantum-regisztráció, amely $U $.</span><span class="sxs-lookup"><span data-stu-id="e875e-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="e875e-113">Ha a \ket{\phi} $ $U $ eigenstate tárolja, akkor $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi\in (-\pi, \pi] $ ismeretlen fázis.</span><span class="sxs-lookup"><span data-stu-id="e875e-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="e875e-114">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e875e-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="e875e-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e875e-115">Remarks</span></span>

<span data-ttu-id="e875e-116">A nagyszámú lekérdezés korlátozása esetén Cramer-Rao a $ \phi $ értékre vonatkozó becslések szórását a $ \sigma \ge 2 \pi/\text{# of lekérdezések} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="e875e-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="e875e-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="e875e-117">References</span></span>

- <span data-ttu-id="e875e-118">Univerzális Single-Qubit-Gate-Set robusztus, robusztus fázisú kiértékelése: Shelby Kimmel, Guang felfüggeszti Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="e875e-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>