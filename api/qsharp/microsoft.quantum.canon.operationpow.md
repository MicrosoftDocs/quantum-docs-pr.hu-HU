---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715769"
---
# <a name="operationpow-function"></a>OperationPow függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Kivált egy műveletet egy hatványra.

Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) 

A megismételni kívánt kaput jelző művelet $U $.


### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)

Ennyi alkalommal kell megismételni a $U $ értéket.



## <a name="output--t--unit"></a>Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A bekapcsolni kívánt művelet típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. Quantum. Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. Quantum. Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)