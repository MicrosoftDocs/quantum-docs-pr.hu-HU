---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 3c0f6cf084311598346b25dd7028e290946cd87f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216285"
---
# <a name="continuousphaseestimationiteration-operation"></a>ContinuousPhaseEstimationIteration művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy iterációs (klasszikusan vezérelt) fázis-értékelési algoritmus egyszeri ismétlését hajtja végre, amely egy egységes Oracle tetszőleges valós hatáskörét használja.

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Egy Double $t $ és egy regiszteren alapuló művelet, amely $U ^ t $-t alkalmazza az adott regiszterre, ahol a $U $ az az egységes, amelynek a fázisát meg kell becsülni, és ahol a $t $ az Oracle számára adott egész szám.


### <a name="time--double"></a>idő: [Double](xref:microsoft.quantum.lang-ref.double)

Az adott egységes Oracle alkalmazási idejének száma.


### <a name="theta--double"></a>THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)

A vezérlő qubit fázisának megfordítására szolgáló szög, mielőtt a cél állapotba lépnek.


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Az adott egységes Oracle által elvégezett állapot regisztrálása.


### <a name="controlqubit--qubit"></a>controlQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

