---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724004"
---
# <a name="preparechoistate-operation"></a>PrepareChoiState művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


Előkészíti a Choi – Jamiłkowski állapotot egy adott művelethez az adott referenciára és a cél-regisztrációra.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="op--qubit--unit"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

A $ \Lambda $, amelynek Choi-Jamiłkowski State $J (\Lambda)/2 ^ N $ értéket elő kell készíteni, ahol a $N $ érték azon qubits száma, amelyeken a művelet `op` működik.


### <a name="reference--qubit"></a>hivatkozás: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A $ \ket{00\cdots 0} $ állapottól kezdődő qubits-regisztráció a műveletre mutató hivatkozásként való használatra `op` .


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A qubits-regisztráció kezdetben a $ \ket{00\cdots 0} $ állapotban van, amelyre `op` alkalmazni kell.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A Jamiłkowski State $J (\Lambda) $ of a kvantum-folyamat értéke $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $, ahol $ | A X\rangle \! \rangle $ egy mátrix $X $ *vektorizációt* az oszlop-halmozási konvencióban. Az állapot klasszikus leírásának megismerése teljes körű információt nyújt a $ \Lambda $ működéséről, amely tetszőleges bemeneti állapotokra támaszkodik, és a *Quantum Process tomográfia* alapját képezi.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. előkészítés. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Quantum. előkészítés. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Quantum. előkészítés. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)