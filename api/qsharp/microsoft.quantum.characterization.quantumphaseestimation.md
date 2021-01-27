---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839663"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Végrehajtja a kvantum fázis becslési algoritmusát egy adott Oracle esetében `U` `targetState` , és beolvassa a fázist egy nagy endian kvantum-regisztrációba.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Egy művelet, amely $U ^ m $ értéket valósít meg az adott egész számra (m).


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A (z) $ \ket{\phi} $ állapotot jelölő Quantum Register $U $. Ha a $ \ket{\phi} $ $U $ eigenstate, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi \in [0, 2 \ PI) $ ismeretlen fázis.


### <a name="controlregister--bigendian"></a>controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Egy big-endian ábrázolási egész számú regiszter, amely a megadott Oracle szabályozására használható, és amely a művelet alkalmazását követően a $ \phi $ ábrázolását fogja tartalmazni. A controlRegister feltételezi, hogy a kezdeti állapotban $ \ket{00\cdots 0} $, ahol a regisztráció hossza a kívánt pontosságot jelzi.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

