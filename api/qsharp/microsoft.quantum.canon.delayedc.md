---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: a1f2582668131816b774bf4a8b7476d9f1ee8cad
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840560"
---
# <a name="delayedc-function"></a>DelayedC függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet


### <a name="arg--t"></a>ARG: nem

Az a bemenet, amelyre a művelet `op` vonatkozik.



## <a name="output--unit--unit--is-ctl"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy új művelet, amely `op` a bemenetre vonatkozik `arg`

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A késleltetni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. késleltetve](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. delay](xref:Microsoft.Quantum.Canon.Delay)