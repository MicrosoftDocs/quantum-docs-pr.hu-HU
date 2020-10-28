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
# <a name="randomwalkphaseestimation-operation"></a>RandomWalkPhaseEstimation művelet

Névtér: [Microsoft. Quantum. Research. jellemzése](xref:Microsoft.Quantum.Research.Characterization)

Csomag [](https://nuget.org/packages/)


Elvégzi az iterációs fázisok becslését egy véletlenszerű lépéssel, hogy megközelítse az adott Oracle-és eigenstate klasszikus mérési eredményeinek a többhelyes tesztelését.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Bevitel

### <a name="initialmean--double"></a>initialMean: [dupla](xref:microsoft.quantum.lang-ref.double)

A kezdeti normál korábbi eloszlás átlaga a $ \phi $-nél.


### <a name="initialstddev--double"></a>initialStdDev: [dupla](xref:microsoft.quantum.lang-ref.double)

A kezdeti normál korábbi eloszlás szórása a $ \phi $ felett.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

A végső posteriori becslésbe elfogadandó mérések száma.


### <a name="maxmeasurements--int"></a>maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

A művelet végrehajtása előtt elvégzendő mérések teljes száma.


### <a name="unwind--int"></a>felcsévélés: [int](xref:microsoft.quantum.lang-ref.int)

A konzisztencia-ellenőrzések meghiúsulása esetén felejtse a találatok számát.


### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Egy olyan, egységes $U $ értékű művelet, amely $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $, ismeretlen fázis: $ \phi \in \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Regisztrálja, hogy $U $.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

A végleges becslés $ \hat{\phi} \mathrel{: =} \expect [\phi] $, ahol a várt érték az összes elfogadott adat után a hátsó.

## <a name="remarks"></a>Megjegyzések

### <a name="iterative-phase-estimation-and-eigenstates"></a>Iterációs fázis becslése és Eigenstates

Általánosságban elmondható, hogy a bemeneti regisztrációnak `eigenstate` nem kell eigenstate $ \ket{\phi} $ $U $-nak lennie, de eigenstates is lehet. Tegyük fel, hogy a bemeneti állapotot a \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align}, ahol a $ \{ \alpha \_ j \} $ olyan összetett együtthatók, mint a $ \sum \_ j | \alpha \_ j | ^ 2 = $1, ahol $U \ket{\phi \_ j} = \phi \_ j\ket {\ Phi \_ j} $.

Ezután az iterációs fázis becslésének végrehajtása végül egyetlen eigenstate konvergál, a [fejlesztési útmutatóban](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)leírtak szerint.

### <a name="experiment-design"></a>Kísérlet kialakítása

A `oracle` \begin{align} \theta \Sim \Pr (\phi), \quad t \approx \frac {\variance{\phi}}.) által megadott mérési idő $t $ *és a* deverziós $ \theta $ átadott értéknek megfelelően van kiválasztva. {1}
a \end{align} ez a heurisztikus megoldás optimálisan csökkenti a várt posteriori eltérést az iterációs fázisok becslésében a normál előtt.

### <a name="optimality"></a>Optimális működés

Ezzel a művelettel közelíthető meg a $ \phi $ fázis optimális kiértékelése, a másodfokú veszteség $L (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $ használatával.

Az iterációs fázis becslésével kapcsolatos további részletekért tekintse meg a [Bayes fázis becslését](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .

## <a name="references"></a>Referencia

- Komphajó és *szerzőtársai 2011* [Doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [Doi: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe és granade 2018 *(előkészítés)* .