---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710882"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="fb39d-102">RandomWalkPhaseEstimation művelet</span><span class="sxs-lookup"><span data-stu-id="fb39d-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="fb39d-103">Névtér: [Microsoft. Quantum. Research. jellemzése](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="fb39d-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="fb39d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb39d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb39d-105">Elvégzi az iterációs fázisok becslését egy véletlenszerű lépéssel, hogy megközelítse az adott Oracle-és eigenstate klasszikus mérési eredményeinek a többhelyes tesztelését.</span><span class="sxs-lookup"><span data-stu-id="fb39d-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="fb39d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fb39d-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="fb39d-107">initialMean: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb39d-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb39d-108">A kezdeti normál korábbi eloszlás átlaga a $ \phi $-nél.</span><span class="sxs-lookup"><span data-stu-id="fb39d-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="fb39d-109">initialStdDev: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb39d-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb39d-110">A kezdeti normál korábbi eloszlás szórása a $ \phi $ felett.</span><span class="sxs-lookup"><span data-stu-id="fb39d-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="fb39d-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb39d-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb39d-112">A végső posteriori becslésbe elfogadandó mérések száma.</span><span class="sxs-lookup"><span data-stu-id="fb39d-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="fb39d-113">maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb39d-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb39d-114">A művelet végrehajtása előtt elvégzendő mérések teljes száma.</span><span class="sxs-lookup"><span data-stu-id="fb39d-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="fb39d-115">felcsévélés: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fb39d-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fb39d-116">A konzisztencia-ellenőrzések meghiúsulása esetén felejtse a találatok számát.</span><span class="sxs-lookup"><span data-stu-id="fb39d-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="fb39d-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="fb39d-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="fb39d-118">Egy olyan, egységes $U $ értékű művelet, amely $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $, ismeretlen fázis: $ \phi \in \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="fb39d-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="fb39d-119">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fb39d-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fb39d-120">Regisztrálja, hogy $U $.</span><span class="sxs-lookup"><span data-stu-id="fb39d-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="fb39d-121">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fb39d-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fb39d-122">A végleges becslés $ \hat{\phi} \mathrel{: =} \expect [\phi] $, ahol a várt érték az összes elfogadott adat után a hátsó.</span><span class="sxs-lookup"><span data-stu-id="fb39d-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb39d-123">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fb39d-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="fb39d-124">Iterációs fázis becslése és Eigenstates</span><span class="sxs-lookup"><span data-stu-id="fb39d-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="fb39d-125">Általánosságban elmondható, hogy a bemeneti regisztrációnak `eigenstate` nem kell eigenstate $ \ket{\phi} $ $U $-nak lennie, de eigenstates is lehet.</span><span class="sxs-lookup"><span data-stu-id="fb39d-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="fb39d-126">Tegyük fel, hogy a bemeneti állapotot a \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align}, ahol a $ \{ \alpha \_ j \} $ olyan összetett együtthatók, mint a $ \sum \_ j | \alpha \_ j | ^ 2 = $1, ahol $U \ket{\phi \_ j} = \phi \_ j\ket {\ Phi \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="fb39d-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="fb39d-127">Ezután az iterációs fázis becslésének végrehajtása végül egyetlen eigenstate konvergál, a [fejlesztési útmutatóban](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="fb39d-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="fb39d-128">Kísérlet kialakítása</span><span class="sxs-lookup"><span data-stu-id="fb39d-128">Experiment Design</span></span>

<span data-ttu-id="fb39d-129">A `oracle` \begin{align} \theta \Sim \Pr (\phi), \quad t \approx \frac {\variance{\phi}}.) által megadott mérési idő $t $ *és a* deverziós $ \theta $ átadott értéknek megfelelően van kiválasztva. {1}</span><span class="sxs-lookup"><span data-stu-id="fb39d-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic* , \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="fb39d-130">a \end{align} ez a heurisztikus megoldás optimálisan csökkenti a várt posteriori eltérést az iterációs fázisok becslésében a normál előtt.</span><span class="sxs-lookup"><span data-stu-id="fb39d-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="fb39d-131">Optimális működés</span><span class="sxs-lookup"><span data-stu-id="fb39d-131">Optimality</span></span>

<span data-ttu-id="fb39d-132">Ezzel a művelettel közelíthető meg a $ \phi $ fázis optimális kiértékelése, a másodfokú veszteség $L (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $ használatával.</span><span class="sxs-lookup"><span data-stu-id="fb39d-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="fb39d-133">Az iterációs fázis becslésével kapcsolatos további részletekért tekintse meg a [Bayes fázis becslését](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="fb39d-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="fb39d-134">Referencia</span><span class="sxs-lookup"><span data-stu-id="fb39d-134">References</span></span>

- <span data-ttu-id="fb39d-135">Komphajó és *szerzőtársai 2011* [Doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="fb39d-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="fb39d-136">Wiebe *et al.* 2013 [Doi: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="fb39d-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="fb39d-137">Wiebe és granade 2018 *(előkészítés)* .</span><span class="sxs-lookup"><span data-stu-id="fb39d-137">Wiebe and Granade 2018 *(in preparation)* .</span></span>