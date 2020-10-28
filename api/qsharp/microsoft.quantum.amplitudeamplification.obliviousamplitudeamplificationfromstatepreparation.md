---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721834"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


A részleges reflexiók esetében az amplitúdó-erősítést az Oracles okozta.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="phases--reflectionphases"></a>fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Részleges tükrözések fázisai


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Az egységes Oracle $A $, amely előkészíti a kiegészítő indítási állapotot


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Egységes Oracle $O $ típusú, `ObliviousOracle` amely közösen működik a kiegészítő és a rendszerregisztráción


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index – qubit jelző regisztrálása



## <a name="output--qubitqubit--unit-adj--ctl"></a>Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

Egy művelet, amely a részleges reflexiók alapján elismeri az amplitúdó-erősítést.

## <a name="remarks"></a>Megjegyzések

Ez szigorúbb feltételeket ró a kisegítő kezdő és megcélzott állapotok formájára, mint a-ben `AmpAmpObliviousByReflectionPhases` .
Feltételezzük, hogy $A \ket {0} \_ f\ket {0} \_ a = \ket{\text{Start}} \_ {fa} $ előkészíti a kiegészítő indítási állapotot $ \ket{\text{Start}} \_ {fa} $-re a számítási alap $ \ket {0} \_ f\ket {0} $ értékről.
Feltételezzük, hogy a megcélzott állapotot $ \ket f $ jelöléssel jelölte meg {1} \_ .
Feltételezzük, hogy a \begin{align} O\ket {\ Text {Start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Anything}} \_ a\ket {\ Text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} egyes egységes $U $-hoz.