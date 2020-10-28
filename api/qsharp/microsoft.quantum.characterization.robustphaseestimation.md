---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714942"
---
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


Elvégzi a robusztus, nem ismétlődő kvantum-értékelési algoritmust egy adott Oracle `U` -és eigenstate esetében, és egyetlen valós értékű becslést nyújt a fázisról a Heisenberg korláton belüli variancia-méretezéssel.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Bevitel

### <a name="bitsprecision--int"></a>bitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)

Ez becslést ad a $ \phi $-re a standard szintű szórással ($ \sigma \Le 2 \ pi/2 ^ \text{bitsPrecision} $) a több lekérdezéssel, például a $ \sigma \Le 10,7 \pi/\text{# of kérdezgető} $ méretezéssel.


### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Egy művelet, amely $U ^ millió $ értéket implementál a megadott egész számra $m $.


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Egy kvantum-regisztráció, amely $U $. Ha a \ket{\phi} $ $U $ eigenstate tárolja, akkor $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi\in (-\pi, \pi] $ ismeretlen fázis.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Megjegyzések

A nagyszámú lekérdezés korlátozása esetén Cramer-Rao a $ \phi $ értékre vonatkozó becslések szórását a $ \sigma \ge 2 \pi/\text{# of lekérdezések} $ értékre.

## <a name="references"></a>Referencia

- Univerzális Single-Qubit-Gate-Set robusztus, robusztus fázisú kiértékelése: Shelby Kimmel, Guang felfüggeszti Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677