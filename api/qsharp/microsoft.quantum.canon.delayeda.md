---
uid: Microsoft.Quantum.Canon.DelayedA
title: Késleltetett függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 33ff4dab36a6c6e17b9496a623f70b814c9f2fed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207071"
---
# <a name="delayeda-function"></a>Késleltetett függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-adj"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet


### <a name="arg--t"></a>ARG: nem

Az a bemenet, amelyre a művelet `op` vonatkozik.



## <a name="output--unit--unit--is-adj"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit)

Egy új művelet, amely `op` a bemenetre vonatkozik `arg`

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A késleltetni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. késleltetve](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. delay](xref:Microsoft.Quantum.Canon.Delay)