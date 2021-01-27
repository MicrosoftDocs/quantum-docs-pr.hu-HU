---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846003"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="b6df9-102">RandomWalkPhaseEstimation művelet</span><span class="sxs-lookup"><span data-stu-id="b6df9-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="b6df9-103">Névtér: [Microsoft. Quantum. Research. jellemzése](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="b6df9-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="b6df9-104">Csomag: [Microsoft. Quantum. Research. jellemzés](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="b6df9-104">Package: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span></span>


<span data-ttu-id="b6df9-105">Elvégzi az iterációs fázisok becslését egy véletlenszerű lépéssel, hogy megközelítse az adott Oracle-és eigenstate klasszikus mérési eredményeinek a többhelyes tesztelését.</span><span class="sxs-lookup"><span data-stu-id="b6df9-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="b6df9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b6df9-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="b6df9-107">initialMean: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6df9-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6df9-108">A kezdeti normál korábbi eloszlás átlaga a $ \phi $-nél.</span><span class="sxs-lookup"><span data-stu-id="b6df9-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="b6df9-109">initialStdDev: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6df9-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6df9-110">A kezdeti normál korábbi eloszlás szórása a $ \phi $ felett.</span><span class="sxs-lookup"><span data-stu-id="b6df9-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="b6df9-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6df9-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6df9-112">A végső posteriori becslésbe elfogadandó mérések száma.</span><span class="sxs-lookup"><span data-stu-id="b6df9-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="b6df9-113">maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6df9-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6df9-114">A művelet végrehajtása előtt elvégzendő mérések teljes száma.</span><span class="sxs-lookup"><span data-stu-id="b6df9-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="b6df9-115">felcsévélés: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6df9-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6df9-116">A konzisztencia-ellenőrzések meghiúsulása esetén felejtse a találatok számát.</span><span class="sxs-lookup"><span data-stu-id="b6df9-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="b6df9-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="b6df9-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="b6df9-118">Egy olyan, egységes $U $ értékű művelet, amely $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $, ismeretlen fázis: $ \phi \in \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="b6df9-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="b6df9-119">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b6df9-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b6df9-120">Regisztrálja, hogy $U $.</span><span class="sxs-lookup"><span data-stu-id="b6df9-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="b6df9-121">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6df9-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6df9-122">A végleges becslés $ \hat{\phi} \mathrel{: =} \expect [\phi] $, ahol a várt érték az összes elfogadott adat után a hátsó.</span><span class="sxs-lookup"><span data-stu-id="b6df9-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6df9-123">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b6df9-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="b6df9-124">Iterációs fázis becslése és Eigenstates</span><span class="sxs-lookup"><span data-stu-id="b6df9-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="b6df9-125">Általánosságban elmondható, hogy a bemeneti regisztrációnak `eigenstate` nem kell eigenstate $ \ket{\phi} $ $U $-nak lennie, de eigenstates is lehet.</span><span class="sxs-lookup"><span data-stu-id="b6df9-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="b6df9-126">Tegyük fel, hogy a bemeneti állapotot a \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align}, ahol a $ \{ \alpha \_ j \} $ olyan összetett együtthatók, mint a $ \sum \_ j | \alpha \_ j | ^ 2 = $1, ahol $U \ket{\phi \_ j} = \phi \_ j\ket {\ Phi \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="b6df9-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="b6df9-127">Ezután az iterációs fázis becslésének végrehajtása végül egyetlen eigenstate konvergál, a [fejlesztési útmutatóban](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="b6df9-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="b6df9-128">Kísérlet kialakítása</span><span class="sxs-lookup"><span data-stu-id="b6df9-128">Experiment Design</span></span>

<span data-ttu-id="b6df9-129">A `oracle` \begin{align} \theta \Sim \Pr (\phi), \quad t \approx \frac {\variance{\phi}}.) által megadott mérési idő $t $ *és a* deverziós $ \theta $ átadott értéknek megfelelően van kiválasztva. {1}</span><span class="sxs-lookup"><span data-stu-id="b6df9-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic*, \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="b6df9-130">a \end{align} ez a heurisztikus megoldás optimálisan csökkenti a várt posteriori eltérést az iterációs fázisok becslésében a normál előtt.</span><span class="sxs-lookup"><span data-stu-id="b6df9-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="b6df9-131">Optimális működés</span><span class="sxs-lookup"><span data-stu-id="b6df9-131">Optimality</span></span>

<span data-ttu-id="b6df9-132">Ezzel a művelettel közelíthető meg a $ \phi $ fázis optimális kiértékelése, a másodfokú veszteség $L (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $ használatával.</span><span class="sxs-lookup"><span data-stu-id="b6df9-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="b6df9-133">Az iterációs fázis becslésével kapcsolatos további részletekért tekintse meg a [Bayes fázis becslését](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="b6df9-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="b6df9-134">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="b6df9-134">References</span></span>

- <span data-ttu-id="b6df9-135">Komphajó és *szerzőtársai 2011* [Doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="b6df9-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="b6df9-136">Wiebe *et al.* 2013 [Doi: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="b6df9-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="b6df9-137">Wiebe és granade 2018 *(előkészítés)*.</span><span class="sxs-lookup"><span data-stu-id="b6df9-137">Wiebe and Granade 2018 *(in preparation)*.</span></span>