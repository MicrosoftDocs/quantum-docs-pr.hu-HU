---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841823"
---
# <a name="applyifelsebc-operation"></a>ApplyIfElseBC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A klasszikus bit értékétől függően két ellenőrizhető művelet egyikét alkalmazza.

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Leírás

Adott `bit` esetben a műveletet a `trueOp` bemenetként alkalmazza, ha a `trueInput` `bit` értéke `true` , és `falseOp(falseInput)` Ha a értéke, akkor alkalmazza `bit` `false` .

## <a name="input"></a>Bevitel

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

A logikai érték, amellyel megállapítható, hogy `trueOp` alkalmazva van-e vagy sem `falseOp` .


### <a name="trueop--t--unit--is-ctl"></a>trueOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az a-re alkalmazandó, ellenőrizhető művelet `bit` `true` .


### <a name="trueinput--t"></a>trueInput: nem

A következőhöz megadott bemenet: `trueOp` `bit` `true` .


### <a name="falseop--u--unit--is-ctl"></a>falseOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az a-re alkalmazandó, ellenőrizhető művelet `bit` `false` .


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