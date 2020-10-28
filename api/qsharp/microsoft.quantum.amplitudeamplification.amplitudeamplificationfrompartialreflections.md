---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721947"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a>AmplitudeAmplificationFromPartialReflections függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


Az amplitúdó erősítése részleges reflexiók használatával.

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="phases--reflectionphases"></a>fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Részleges tükrözések fázisai


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

A Start állapottal kapcsolatos reflexiós operátor


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Megcélzott állapottal kapcsolatos reflexiós operátor



## <a name="output--qubit--unit-adj--ctl"></a>Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

Egy művelet, amely az amplitúdó-erősítést részleges reflexiók használatával valósítja meg.

## <a name="remarks"></a>Megjegyzések

Az amplitúdó-erősítés olyan különleges eset, ha a rendszer nem rendelkezik qubits, és a feledékeny Oracle az identitásra van állítva.
A legtöbb esetben az a $ `startQubits` \ket{\text{start}} $1 állapotú \_ , amely a $-$1 eigenstate lesz inicializálva `startStateReflection` .