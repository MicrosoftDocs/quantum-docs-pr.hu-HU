---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: ApplyWithA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: f1ff31da53952931426d358cbedad44a50d87f5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716930"
---
# <a name="applywitha-operation"></a>ApplyWithA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


A két művelet miatt a rendszer az egyiket a másikkal konjugáltként alkalmazza.

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit
```


## <a name="description"></a>Leírás

A két művelet, illetve a $U $ és a $V $ közötti, az egységes operátorok által leírt módon alkalmazza őket a következő sorrendben: $U ^ {\dagger} V U $. Ez a művelet megvalósítja a $V $ konjugált $U $-vel való összeláncolását.

## <a name="input"></a>Bevitel

### <a name="outeroperation--t--unit-adj"></a>outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj

$U $ művelet, amelyet a $V $ konjugátumhoz kell használni. Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.


### <a name="inneroperation--t--unit-adj"></a>innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj

Az a művelet, $V $ konjugált.


### <a name="target--t"></a>cél: nem

A külső és belső műveletekhez megadott bemenet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelyen az egyes belső és külső műveletek működnek.

## <a name="remarks"></a>Megjegyzések

A külső művelet mindig adjointable, de nem szükséges ahhoz, hogy az összevont művelet ellenőrizhető legyen, és ne legyenek ellenőrizhetők.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft. Quantum. Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)