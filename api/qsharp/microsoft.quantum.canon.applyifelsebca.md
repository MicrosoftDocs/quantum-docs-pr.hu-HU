---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: d36b16298ea177f16b7bbb260f069bfe35b9a72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218631"
---
# <a name="applyifelsebca-operation"></a>ApplyIfElseBCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy klasszikus bites értéktől függően két egységes művelet egyikét alkalmazza.

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Adott `bit` esetben a műveletet a `trueOp` bemenetként alkalmazza, ha a `trueInput` `bit` értéke `true` , és `falseOp(falseInput)` Ha a értéke, akkor alkalmazza `bit` `false` .

## <a name="input"></a>Bevitel

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

A logikai érték, amellyel megállapítható, hogy `trueOp` alkalmazva van-e vagy sem `falseOp` .


### <a name="trueop--t--unit--is-adj--ctl"></a>trueOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Az a művelet, amelyre alkalmazni kell `bit` `true` .


### <a name="trueinput--t"></a>trueInput: nem

A következőhöz megadott bemenet: `trueOp` `bit` `true` .


### <a name="falseop--u--unit--is-adj--ctl"></a>falseOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Az a művelet, amelyre alkalmazni kell `bit` `false` .


### <a name="falseinput--u"></a>falseInput: ' U

A következőhöz megadott bemenet: `falseOp` `bit` `false` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A `trueOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.
### <a name="u"></a>' U

A `falseOp` feltételesen alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)