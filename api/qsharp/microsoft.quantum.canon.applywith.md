---
uid: Microsoft.Quantum.Canon.ApplyWith
title: ApplyWith művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWith
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: fd46f84e30e72672967b90d92f507d2a5c438dba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217305"
---
# <a name="applywith-operation"></a>ApplyWith művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A két művelet miatt a rendszer az egyiket a másikkal konjugáltként alkalmazza.

```qsharp
operation ApplyWith<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit), target : 'T) : Unit
```


## <a name="description"></a>Leírás

A két művelet, illetve a $U $ és a $V $ közötti, az egységes operátorok által leírt módon alkalmazza őket a következő sorrendben: $U ^ {\dagger} V U $. Ez a művelet megvalósítja a $V $ konjugált $U $-vel való összeláncolását.

## <a name="input"></a>Bevitel

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

$U $ művelet, amelyet a $V $ konjugátumhoz kell használni. Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.


### <a name="inneroperation--t--unit"></a>innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) 

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

- [Microsoft. Quantum. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft. Quantum. Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)