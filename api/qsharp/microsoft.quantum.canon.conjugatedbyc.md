---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 622b1d93dcbd02d000a68de23c66537b24d36c99
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840841"
---
# <a name="conjugatedbyc-function"></a>ConjugatedByC függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az adott külső és belső műveletek olyan új műveletet adnak vissza, amely a belső műveletet a külső művelettel végzi.

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a>Bevitel

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

$U $ művelet, amelyet a $V $ konjugátumhoz kell használni. Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.


### <a name="inneroperation--t--unit--is-ctl"></a>innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az a művelet, $V $ konjugált.



## <a name="output--t--unit--is-ctl"></a>Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy új művelet, amelynek a műveletét az egységes $U ^ {\dagger} V U $ jelképezi.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Annak a célnak a típusa, amelyen a belső és a külső műveletek működnek.

## <a name="remarks"></a>Megjegyzések

A külső művelet mindig adjointable, de nem szükséges ahhoz, hogy az összevont művelet ellenőrizhető legyen, és ne legyenek ellenőrizhetők.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ConjugatedBy](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)