---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721750"
---
# <a name="standardamplitudeamplification-function"></a>StandardAmplitudeAmplification függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


Standard amplitúdó-erősítési algoritmus

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="niterations--int"></a>nIterations: [int](xref:microsoft.quantum.lang-ref.int)

Ismétlések száma $n $ amplitúdó-erősítéssel


### <a name="stateoracle--stateoracle"></a>stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Az egységes Oracle $A $, amely előkészíti az indítási állapotot


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Index a qubit jelzőhöz



## <a name="output--qubit--unit-adj--ctl"></a>Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

A standard amplitúdó-erősítési kvantum-algoritmust megvalósító művelet

## <a name="remarks"></a>Megjegyzések

Ez a szabványos amplitúdó-erősítési algoritmus, amely a kiszámított gondolkodási fázisok alapján lett kiszámítva `AmpAmpPhasesStandard` , feltételezve, hogy a \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} ez a művelet előkészíti a \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket f\ket {1} \_ {\ Text {Target}} \_ s + \cdots\ket {0} \_ f \end{align} a legtöbb esetben, `flagQubit` és `auxiliaryRegister` inicializálása a {0} \_ $ \ket f\ket {0} \_ a $ értékkel történik.

## <a name="references"></a>Referencia

- [*G. Brassard, P. Hoyer, M. Mosca, A. menetfúró*](https://arxiv.org/abs/quant-ph/0005055)