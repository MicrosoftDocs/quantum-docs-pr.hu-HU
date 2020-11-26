---
uid: Microsoft.Quantum.Canon.Delayed
title: Késleltetett függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216455"
---
# <a name="delayed-function"></a>Késleltetett függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Bevitel

### <a name="op--t--u"></a>op: 'T => ' U 

Egy alkalmazni kívánt művelet.


### <a name="arg--t"></a>ARG: nem

Az a bemenet, amelyre a művelet vonatkozik.



## <a name="output--unit--u"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => U 

Egy új művelet, amely `op` a bemenetre vonatkozik `arg`

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A késleltetni kívánt művelet bemeneti típusa.
### <a name="u"></a>' U

A késleltetni kívánt művelet visszatérési típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft. Quantum. Canon. késleltetett](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft. Quantum. Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft. Quantum. Canon. delay](xref:Microsoft.Quantum.Canon.Delay)