---
uid: Microsoft.Quantum.Canon.DelayA
title: Késleltetési művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207139"
---
# <a name="delaya-operation"></a>Késleltetési művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy megadott műveletet késleltetve alkalmaz.

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a>Leírás

Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.
A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.
`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-adj"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

Egy alkalmazni kívánt művelet.


### <a name="arg--t"></a>ARG: nem

Az a bemenet, amelyre a művelet vonatkozik.


### <a name="aux--unit"></a>AUX: [egység](xref:microsoft.quantum.lang-ref.unit)

A művelet alkalmazásának a részleges alkalmazás használatával történő késleltetésére szolgáló argumentum.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A késleltetni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. Quantum. Canon. késleltetve](xref:Microsoft.Quantum.Canon.Delayed)