---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721877"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>ApplyObliviousAmplitudeAmplification művelet

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


A részleges reflexiók megadásával megfeledkezett az amplitúdó-erősítésről.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="phases--reflectionphases"></a>fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Részleges tükrözések fázisai


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

A kiegészítő regisztráció indítási állapotával kapcsolatos reflexiós operátor


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

A kiegészítő regiszter megcélzott állapotával kapcsolatos reflexiós operátor


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Egységes Oracle $O $ típusú, `ObliviousOracle` amely közösen működik a kiegészítő és a rendszerregisztrálók esetében.


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Kiegészítő regisztráció


### <a name="systemregister--qubit"></a>systemRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rendszerregisztráció



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Egy adott kiegészítő indítási állapothoz $ \ket{\text{Start}} \_ a $, egy adott kiegészítő megcélzott állapot $ \ket{\text{Target}} $ \_ és minden rendszerállapot $ \ket{\psi} \_ s $, tegyük fel, hogy a \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{target} ^ \perp} \_ a\cdots \end{align} néhány egységes $U $.
A kezdő és a cél állapotokra vonatkozó, az alkalmazások és a adjoint által összekapcsolt kiegészítő regisztráció során felmerülő reflexiók sorozatából az `signalOracle` U alkalmazásának sikerességi valószínűsége módosítható.

A legtöbb esetben `auxiliaryRegister` a a $ \ket{\text{Start}} állapotban van inicializálva \_ .

## <a name="references"></a>Referencia

Lásd:

- [ *DW Berry, am Childs, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) a standard verzióhoz.
  Lásd:
- [ *Alacsony G.H., I.L.*](https://arxiv.org/abs/1610.06546) a részleges tükrözések általánosításához.