---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715320"
---
# <a name="transformedoperationca-function"></a>TransformedOperationCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy függvény és egy művelet miatt egy új műveletet ad vissza, amelynek a bemenetét az adott függvény átalakítja.

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="fn--u---t"></a>FN: U-> 'T

Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.


### <a name="op--t--unit-adj--ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

Az átalakítandó művelet.



## <a name="output--u--unit-adj--ctl"></a>Kimenet: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

Egy új művelet tbat hívja a `fn` bemenetét, majd átadja az eredményül kapott kimenetet `op` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="u"></a>' U



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [Microsoft. Quantum. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. Quantum. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. komponált](xref:Microsoft.Quantum.Canon.Composed)