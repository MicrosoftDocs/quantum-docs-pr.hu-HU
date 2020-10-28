---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714943"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


Végrehajtja a kvantum fázis becslési algoritmusát egy adott Oracle esetében `U` `targetState` , és beolvassa a fázist egy nagy endian kvantum-regisztrációba.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Bevitel

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Egy művelet, amely $U ^ m $ értéket valósít meg az adott egész számra (m).


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A (z) $ \ket{\phi} $ állapotot jelölő Quantum Register $U $. Ha a $ \ket{\phi} $ $U $ eigenstate, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi \in [0, 2 \ PI) $ ismeretlen fázis.


### <a name="controlregister--bigendian"></a>controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Egy big-endian ábrázolási egész számú regiszter, amely a megadott Oracle szabályozására használható, és amely a művelet alkalmazását követően a $ \phi $ ábrázolását fogja tartalmazni. A controlRegister feltételezi, hogy a kezdeti állapotban $ \ket{00\cdots 0} $, ahol a regisztráció hossza a kívánt pontosságot jelzi.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

