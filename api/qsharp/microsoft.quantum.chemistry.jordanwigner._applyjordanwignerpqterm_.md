---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQTerm_
title: _ApplyJordanWignerPQTerm_ művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQTerm_
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: ef9ed8a9361548730d716cf0fea8ff08c82b6f59
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215911"
---
# <a name="_applyjordanwignerpqterm_-operation"></a>_ApplyJordanWignerPQTerm_ művelet

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Alkalmazza az idő-evolúciót az a által leírt PQ kifejezéssel `GeneratorIndex` .

```qsharp
operation _ApplyJordanWignerPQTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, extraParityQubits : Qubit[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="term--generatorindex"></a>kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` egy PQ kifejezést jelölő kifejezés.


### <a name="stepsize--double"></a>stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

Az idő időbeli alakulása.


### <a name="extraparityqubits--qubit"></a>extraParityQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Nem kötelező paritásos qubits, amely a Time-Evolution (időbeli) változását tükrözi.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A Hamilton qubits.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

