---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852381"
---
# <a name="operationpow-function"></a>OperationPow függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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