---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209485"
---
# <a name="applyifelserc-operation"></a>ApplyIfElseRC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A klasszikus eredmények értékétől függően két ellenőrizhető művelet egyikét alkalmazza.

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Leírás

Az eredmény megadásakor `result` a műveletet a `zeroOp` `zeroInput` bemenetként alkalmazza, ha `result` az egyenlő `Zero` , és ha van, `oneOp(oneInput)` akkor alkalmazza `result == One` .

## <a name="input"></a>Bevitel

### <a name="result--__invalidresult__"></a>eredmény: __érvénytelen <Result>__

Az a mérési eredmény, amellyel meghatározható, hogy `zeroOp` alkalmazva van-e vagy sem `oneOp` .


### <a name="zeroop--t--unit--is-ctl"></a>zeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az a művelet, amelyre alkalmazni kell a műveletet `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: nem

Az a bemenet, amelyet meg kell adni `zeroOp` `result == Zero` .


### <a name="oneop--u--unit--is-ctl"></a>oneOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az a művelet, amelyre alkalmazni kell a műveletet `result == One` .


### <a name="oneinput--u"></a>oneInput: ' U

Az a bemenet, amelyet meg kell adni `oneOp` `result == One` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A `zeroOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.
### <a name="u"></a>' U

A `oneOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)