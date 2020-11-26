---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 35dc76a06fd4e8c819b785fd4c588f108c918326
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205779"
---
# <a name="operationpowa-function"></a>OperationPowA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kivált egy műveletet egy hatványra.
A módosító `A` azt jelzi, hogy a művelet adjointable.

Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-adj"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

A megismételni kívánt kaput jelző művelet $U $.


### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)

Ennyi alkalommal kell megismételni a $U $ értéket.



## <a name="output--t--unit--is-adj"></a>Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)

Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A bekapcsolni kívánt művelet típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)