---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841813"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A klasszikus eredmények értékétől függően két művelet egyikét alkalmazza.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Leírás

Az eredmény megadásakor `result` a műveletet a `zeroOp` `zeroInput` bemenetként alkalmazza, ha `result` az egyenlő `Zero` , és ha van, `oneOp(oneInput)` akkor alkalmazza `result == One` .

## <a name="input"></a>Bevitel

### <a name="result--__invalidresult__"></a>eredmény: __érvénytelen <Result>__

Az a mérési eredmény, amellyel meghatározható, hogy `zeroOp` alkalmazva van-e vagy sem `oneOp` .


### <a name="zeroop--t--unit"></a>zeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) 

Az a művelet, amelyre alkalmazni kell `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: nem

Az a bemenet, amelyet meg kell adni `zeroOp` `result == Zero` .


### <a name="oneop--u--unit"></a>oneOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) 

Az a művelet, amelyre alkalmazni kell `result == One` .


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