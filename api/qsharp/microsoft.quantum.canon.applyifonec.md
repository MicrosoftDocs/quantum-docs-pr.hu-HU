---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209417"
---
# <a name="applyifonec-operation"></a>ApplyIfOneC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy, a klasszikus eredmény értékének egyikét alkalmazza.

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a>Leírás

`op`A művelet és az eredmény megadott értéke `result` az IF értékre vonatkozik `op` `target` `result` `One` . Ha `Zero` semmi nem történik a következővel: `target` .
Az utótag `C` azt jelzi, hogy az alkalmazni kívánt művelet ellenőrizhető.

## <a name="input"></a>Bevitel

### <a name="result--__invalidresult__"></a>eredmény: __érvénytelen <Result>__

Egy mérési eredmény, amely meghatározza, hogy az op alkalmazva van-e.


### <a name="op--t--unit--is-ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy feltételesen alkalmazni kívánt művelet.


### <a name="target--t"></a>cél: nem

Az a bemenet, amelyre a művelet vonatkozik.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A feltételesen alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. Quantum. Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. Quantum. Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)