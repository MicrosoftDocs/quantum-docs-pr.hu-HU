---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715838"
---
# <a name="multiplexoperations-operation"></a>MultiplexOperations művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


A több állapotú tömb által vezérelt műveletek tömbjét alkalmazza.

Ez azt is alkalmazza, hogy a szorzás által vezérelt egységes művelet $U $, amely egy egységes $V _j $-t alkalmaz, ha $n $-qubit számú állapotot ($ \ket{j} $) szabályozza.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Bevitel

### <a name="unitaries--t--unit-adj--ctl"></a>unitaries: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL []

Akár $2 ^ n $ egységes műveletből álló tömb. A $j $ th műveletet a (\ket{j} $) számú, Little-endian formátumban kódolt számú állapot indexeli.


### <a name="index--littleendian"></a>index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.


### <a name="target--t"></a>cél: nem

Az általános qubit regisztrálja, hogy $V _j $ működik.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

`coefficients` Ha kevesebb, mint $2 ^ n $ érték van megadva, akkor az azonosító elemek kitöltése megtörténik. Ez a megvalósítás $n-$1 kiegészítő qubits használ.

## <a name="references"></a>Referencia

- Az első kvantum-szimuláció felé a kvantum-gyorsulás Andrew M. Childs, Dmitrij Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980