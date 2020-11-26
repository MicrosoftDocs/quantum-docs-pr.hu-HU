---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: fe2babb87d716185286b0864745f7ff6e637f8a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207010"
---
# <a name="delayedca-function"></a>DelayedCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-adj--ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet


### <a name="arg--t"></a>ARG: nem

Az a bemenet, amelyre a művelet `op` vonatkozik.



## <a name="output--unit--unit--is-adj--ctl"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

Egy új művelet, amely `op` a bemenetre vonatkozik `arg`

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A késleltetni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. késleltetve](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. delay](xref:Microsoft.Quantum.Canon.Delay)