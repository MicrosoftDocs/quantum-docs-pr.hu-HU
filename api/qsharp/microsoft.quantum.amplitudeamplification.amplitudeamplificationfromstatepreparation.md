---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721946"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>AmplitudeAmplificationFromStatePreparation függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


A részleges reflexiók esetében az amplitúdó erősítése Oracle-támogatással.

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="phases--reflectionphases"></a>fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Részleges tükrözések fázisai


### <a name="stateoracle--stateoracle"></a>stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Az egységes Oracle $A $, amely előkészíti az indítási állapotot


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index a qubit jelzőhöz



## <a name="output--qubit--unit-adj--ctl"></a>Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

Olyan művelet, amely a részleges reflexiók által megvalósított Oracle-bővítést alkalmaz.

## <a name="remarks"></a>Megjegyzések

Ez szigorúbb feltételeket ró a kezdő és a cél állapotokra, mint a-ben `AmpAmpByReflectionPhases` .
Feltételezzük, hogy a megcélzott állapotot $ \ket f $ jelöléssel jelölte meg {1} \_ .
Feltételezzük, hogy a \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} a legtöbb esetben, `flagQubit` és `auxiliaryRegister` inicializálása a $ \ket {0} \_ {f} \ket {0} \_ s $ állapotban van.