---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721905"
---
# <a name="applyfixedpointamplification-operation"></a>ApplyFixedPointAmplification művelet

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


Fixed-Point amplitúdó-erősítési algoritmus

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="statepreporacle--stateoracle"></a>statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Az egységes Oracle, amely előkészíti a kezdő állapotot.


### <a name="startqubits--qubit"></a>startQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-regisztráció



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A startQubits a $ \ket{0 \cdots 0} $ állapotban kell lennie. Ez a művelet több, $2 $ értékű lekérdezésre mutat be, amíg el nem éri a lekérdezések maximális számát, vagy megtalálhatók a célként megadott állapot.