---
uid: Microsoft.Quantum.Canon.Delay
title: Késleltetési művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840655"
---
# <a name="delay-operation"></a>Késleltetési művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy megadott műveletet késleltetve alkalmaz.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Leírás

Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.
A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.
`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .

## <a name="input"></a>Bevitel

### <a name="op--t--u"></a>op: 'T => ' U 

Egy alkalmazni kívánt művelet.


### <a name="arg--t"></a>ARG: nem

Az a bemenet, amelyre a művelet vonatkozik.


### <a name="aux--unit"></a>AUX: [egység](xref:microsoft.quantum.lang-ref.unit)

A művelet alkalmazásának a részleges alkalmazás használatával történő késleltetésére szolgáló argumentum.



## <a name="output--u"></a>Kimenet: U



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A késleltetni kívánt művelet bemeneti típusa.
### <a name="u"></a>' U

A késleltetni kívánt művelet visszatérési típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft. Quantum. Canon. Delaya](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. Quantum. Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft. Quantum. Canon. késleltetve](xref:Microsoft.Quantum.Canon.Delayed)