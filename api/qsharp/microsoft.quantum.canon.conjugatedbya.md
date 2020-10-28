---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: bcaab28e99d3d61f4a36da866321d28f3dc4bd53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716468"
---
# <a name="conjugatedbya-function"></a>ConjugatedByA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Az adott külső és belső műveletek olyan új műveletet adnak vissza, amely a belső műveletet a külső művelettel végzi.

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a>Bevitel

### <a name="outeroperation--t--unit-adj"></a>outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj

$U $ művelet, amelyet a $V $ konjugátumhoz kell használni. Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.


### <a name="inneroperation--t--unit-adj"></a>innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj

Az a művelet, $V $ konjugált.



## <a name="output--t--unit-adj"></a>Kimenet: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) : Adj

Egy új művelet, amelynek a műveletét az egységes $U ^ {\dagger} V U $ jelképezi.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Annak a célnak a típusa, amelyen a belső és a külső műveletek működnek.

## <a name="remarks"></a>Megjegyzések

A külső művelet mindig adjointable, de nem szükséges ahhoz, hogy az összevont művelet ellenőrizhető legyen, és ne legyenek ellenőrizhetők.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)