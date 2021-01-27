---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: ef92e517ae40e76c94aff1121c78ece9985109fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857711"
---
# <a name="blockencodingreflectionbylcu-function"></a>BlockEncodingReflectionByLCU függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy fontos operátort kódol `BlockEncodingReflection` .

Ez létrehoz egy `BlockEncodingReflection` egységes $U = P\cdot V\cdot P ^ \dagger $-t, amely kódol egy operátort $H = \ sum_ {j} | \ alpha_j | U_j $, amely a unitaries lineáris kombinációja. A $P $ általában egy olyan állapot-előkészítés, amely egy olyan egységes előkészítő, amely $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, és $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Bevitel

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a>statePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy egységes $P $, amely előkészíti a megcélzott állapotot.


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a>választó: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy egységes $V $, amely kódolja $H $ unitaries összetevőjét.



## <a name="output--blockencodingreflection"></a>Kimenet: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

A regisztereken közösen működő, egységes $U $ `a` `s` , amely blokkolja a $H $-t, és megfelel a $U "^ {-1} = U $" kódolásnak.

## <a name="remarks"></a>Megjegyzések

Ez `BlockEncoding` a megvalósítás megadja a tulajdonságait `BlockEncodingReflection` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. szimulációs. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)