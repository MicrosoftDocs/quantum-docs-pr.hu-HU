---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: ce08907646c3210f76244f29aa0d936e2bd6ee43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718204"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy klasszikus bit értékétől függően két adjointable műveletet alkalmaz.

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit
```


## <a name="description"></a>Leírás

Adott `bit` esetben a műveletet a `trueOp` bemenetként alkalmazza, ha a `trueInput` `bit` értéke `true` , és `falseOp(falseInput)` Ha a értéke, akkor alkalmazza `bit` `false` .

## <a name="input"></a>Bevitel

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

A logikai érték, amellyel megállapítható, hogy `trueOp` alkalmazva van-e vagy sem `falseOp` .


### <a name="trueop--t--unit-adj"></a>trueOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj

Az adjointable művelet, amelyre alkalmazni kell `bit` `true` .


### <a name="trueinput--t"></a>trueInput: nem

A következőhöz megadott bemenet: `trueOp` `bit` `true` .


### <a name="falseop--u--unit-adj"></a>falseOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) Adj

Az adjointable művelet, amelyre alkalmazni kell `bit` `false` .


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