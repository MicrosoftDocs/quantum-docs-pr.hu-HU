---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854403"
---
# <a name="preparechoistate-operation"></a>PrepareChoiState művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Előkészíti a Choi – Jamiołkowski állapotot egy adott művelethez az adott referenciára és a cél-regisztrációra.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="op--qubit--unit"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

A $ \Lambda $, amelynek Choi-Jamiołkowski State $J (\Lambda)/2 ^ N $ értéket elő kell készíteni, ahol a $N $ érték azon qubits száma, amelyeken a művelet `op` működik.


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