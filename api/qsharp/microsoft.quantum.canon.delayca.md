---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a8606cde976882bba0eb23467932b9ee0ed36696
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840620"
---
# <a name="delayca-operation"></a>DelayCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy megadott műveletet késleltetve alkalmaz.

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Adott művelet és a művelet bemenete esetén a művelet a további adatok megadása után alkalmazza a műveletet.
A kifejezés `Delay(op, arg, _)` egy olyan művelet, amely `op` a `arg` hívásakor vonatkozik.
`Delay(op,arg,_)`A kifejezés lehetővé teszi az alkalmazás késleltetését `op` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-adj--ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

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