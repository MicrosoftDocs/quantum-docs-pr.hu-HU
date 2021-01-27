---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858162"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy fontos operátort kódol `BlockEncoding` .

Ez létrehoz egy `BlockEncoding` egységes $U = P\cdot V\cdot P ^ \dagger $-t, amely kódol egy operátort $H = \ sum_ {j} | \ alpha_j | U_j $, amely a unitaries lineáris kombinációja. A $P $ általában egy olyan állapot-előkészítés, amely egységes, például $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, és $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy egységes $P $, amely előkészíti a megcélzott állapotot.


### <a name="selector--ts--unit--is-adj--ctl"></a>választó: ('T, 'S) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy egységes $V $, amely kódolja $H $ unitaries összetevőjét.



## <a name="output--ts--unit--is-adj--ctl"></a>Kimenet: ('T, 'S) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

A regisztereken közösen működő, egységes $U $ `a` `s` , amely blokkolja a $H $-ot, és megfelel a $U ^ \Dagger = U $ kódolásnak.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="s"></a>Képgalériája



## <a name="remarks"></a>Megjegyzések

Ez `BlockEncoding` a megvalósítás megadja a tulajdonságait `BlockEncodingReflection` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. szimulációs. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)