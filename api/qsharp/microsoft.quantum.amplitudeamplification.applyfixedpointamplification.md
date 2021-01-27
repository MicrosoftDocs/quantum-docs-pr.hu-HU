---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847235"
---
# <a name="applyfixedpointamplification-operation"></a>ApplyFixedPointAmplification művelet

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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