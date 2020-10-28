---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715671"
---
# <a name="operationpowca-function"></a>OperationPowCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Kivált egy műveletet egy hatványra.
A módosító `A` azt jelzi, hogy a művelet ellenőrizhető és adjointable.

Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit-ctl--adj"></a>op: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj

A megismételni kívánt kaput jelző művelet $U $.


### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)

Ennyi alkalommal kell megismételni a $U $ értéket.



## <a name="output--t--unit-ctl--adj"></a>Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj

Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A bekapcsolni kívánt művelet típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)