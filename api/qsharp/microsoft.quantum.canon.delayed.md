---
uid: Microsoft.Quantum.Canon.Delayed
title: Késleltetett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840588"
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