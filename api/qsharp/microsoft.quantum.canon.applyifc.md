---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: ef16b23349b604d174e72d9ae06d2052e2ab60f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841861"
---
# <a name="applyifc-operation"></a>ApplyIfC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy klasszikus bit-re vonatkozó, ellenőrizhető működést alkalmaz.

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a>Leírás

Ha egy művelet `op` és egy bit érték `bit` van megadva, `op` az a `target` IF értéke lesz `bit` `true` . Ha `false` semmi nem történik a következővel: `target` .
Az utótag `C` azt jelzi, hogy az alkalmazni kívánt művelet ellenőrizhető.

## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy feltételesen alkalmazni kívánt művelet.


### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

egy logikai érték, amely azt szabályozza, hogy az op alkalmazva van-e.


### <a name="target--t"></a>cél: nem

Az a bemenet, amelyre a művelet vonatkozik.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A feltételesen alkalmazni kívánt művelet bemeneti típusa.

## <a name="example"></a>Példa

A következő előkészíti a qubits egy olyan számítási alapon történő regisztrálását, amelyet egy, az értékek tömbje megadott klasszikus bit-sztring képvisel `Bool` :

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. Quantum. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Quantum. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)