---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843935"
---
# <a name="standardamplitudeamplification-function"></a>StandardAmplitudeAmplification függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="output--qubit--unit--is-adj--ctl"></a>Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

A standard amplitúdó-erősítési kvantum-algoritmust megvalósító művelet

## <a name="remarks"></a>Megjegyzések

Ez a szabványos amplitúdó-erősítési algoritmus, amely a kiszámított gondolkodási fázisok alapján lett kiszámítva `AmpAmpPhasesStandard` , feltételezve, hogy a \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} ez a művelet előkészíti a \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket f\ket {1} \_ {\ Text {Target}} \_ s + \cdots\ket {0} \_ f \end{align} a legtöbb esetben, `flagQubit` és `auxiliaryRegister` inicializálása a {0} \_ $ \ket f\ket {0} \_ a $ értékkel történik.

## <a name="references"></a>Hivatkozások

- [*G. Brassard, P. Hoyer, M. Mosca, A. menetfúró*](https://arxiv.org/abs/quant-ph/0005055)