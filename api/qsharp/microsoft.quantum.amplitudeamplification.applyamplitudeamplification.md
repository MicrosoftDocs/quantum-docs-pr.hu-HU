---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721932"
---
# <a name="applyamplitudeamplification-operation"></a>ApplyAmplitudeAmplification művelet

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


Amplitúdó-erősítést alkalmaz egy adott regisztráción, a fázisok és az Oracle-alkalmazások adott készletének használatával, hogy tükrözze a kezdeti és a végső állapotot.

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="phases--reflectionphases"></a>fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Az amplitúdó-erősítési algoritmus egyes lépéseinek részleges tükrözéseit leíró fázisok összessége. Lásd: @"microsoft.quantum.amplitudeamplification.standardreflectionphases" példa.


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Egy Oracle, amely a kezdeti állapotot tükrözi.


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Egy Oracle, amely a kívánt végső állapotot tükrözi.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Egy regisztráció, amely amplitúdó-erősítést hajt végre.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

