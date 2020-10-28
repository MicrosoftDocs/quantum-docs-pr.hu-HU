---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716217"
---
# <a name="delayedca-function"></a>DelayedCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit-ctl--adj"></a>op: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj

A visszatérési érték alkalmazásának eredményeképpen alkalmazandó művelet


### <a name="arg--t"></a>ARG: nem

Az a bemenet, amelyre a művelet `op` vonatkozik.



## <a name="output--unit--unit-ctl--adj"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj

Egy új művelet, amely `op` a bemenetre vonatkozik `arg`

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A késleltetni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. késleltetve](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. delay](xref:Microsoft.Quantum.Canon.Delay)