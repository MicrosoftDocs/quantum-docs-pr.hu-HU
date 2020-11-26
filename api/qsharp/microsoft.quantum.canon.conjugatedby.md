---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: ed5316d4603c31d7db2cd6b0d7e54b56fc750fcb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216727"
---
# <a name="conjugatedby-function"></a>ConjugatedBy függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az adott külső és belső műveletek olyan új műveletet adnak vissza, amely a belső műveletet a külső művelettel végzi.

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>Bevitel

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

$U $ művelet, amelyet a $V $ konjugátumhoz kell használni. Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.


### <a name="inneroperation--t--unit"></a>innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) 

Az a művelet, $V $ konjugált.



## <a name="output--t--unit"></a>Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit) 

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