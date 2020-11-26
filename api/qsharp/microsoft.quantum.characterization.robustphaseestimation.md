---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 3e6774e2fe348668840cdc08fe3a070ec3d82a6d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216081"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="f748a-102">RobustPhaseEstimation művelet</span><span class="sxs-lookup"><span data-stu-id="f748a-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="f748a-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f748a-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="f748a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f748a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f748a-105">Elvégzi a robusztus, nem ismétlődő kvantum-értékelési algoritmust egy adott Oracle `U` -és eigenstate esetében, és egyetlen valós értékű becslést nyújt a fázisról a Heisenberg korláton belüli variancia-méretezéssel.</span><span class="sxs-lookup"><span data-stu-id="f748a-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="f748a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f748a-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="f748a-107">bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f748a-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f748a-108">Ez becslést ad a $ \phi $-re a standard szintű szórással ($ \sigma \Le 2 \ pi/2 ^ \text{bitsPrecision} $) a több lekérdezéssel, például a $ \sigma \Le 10,7 \pi/\text{# of kérdezgető} $ méretezéssel.</span><span class="sxs-lookup"><span data-stu-id="f748a-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="f748a-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="f748a-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="f748a-110">Egy művelet, amely $U ^ millió $ értéket implementál a megadott egész számra $m $.</span><span class="sxs-lookup"><span data-stu-id="f748a-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="f748a-111">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f748a-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f748a-112">Egy kvantum-regisztráció, amely $U $.</span><span class="sxs-lookup"><span data-stu-id="f748a-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="f748a-113">Ha a \ket{\phi} $ $U $ eigenstate tárolja, akkor $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi\in (-\pi, \pi] $ ismeretlen fázis.</span><span class="sxs-lookup"><span data-stu-id="f748a-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="f748a-114">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f748a-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="f748a-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f748a-115">Remarks</span></span>

<span data-ttu-id="f748a-116">A nagyszámú lekérdezés korlátozása esetén Cramer-Rao a $ \phi $ értékre vonatkozó becslések szórását a $ \sigma \ge 2 \pi/\text{# of lekérdezések} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="f748a-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="f748a-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="f748a-117">References</span></span>

- <span data-ttu-id="f748a-118">Univerzális Single-Qubit-Gate-Set robusztus, robusztus fázisú kiértékelése: Shelby Kimmel, Guang felfüggeszti Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="f748a-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>