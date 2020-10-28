---
uid: Microsoft.Quantum.Canon.Delayed
title: Késleltetett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716258"
---
# <a name="delayed-function"></a>Késleltetett függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


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