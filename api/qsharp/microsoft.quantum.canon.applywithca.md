---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: a5ce7dc5ddfbb2fc06743d36614129c371850da2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841145"
---
# <a name="applywithca-operation"></a>ApplyWithCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A két művelet miatt a rendszer az egyiket a másikkal konjugáltként alkalmazza.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

A két művelet, illetve a $U $ és a $V $ közötti, az egységes operátorok által leírt módon alkalmazza őket a következő sorrendben: $U ^ {\dagger} V U $. Ez a művelet megvalósítja a $V $ konjugált $U $-vel való összeláncolását.

## <a name="input"></a>Bevitel

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

$U $ művelet, amelyet a $V $ konjugátumhoz kell használni. Vegye figyelembe, hogy a külső műveletnek $U $ adjointable kell lennie, de nem feltétlenül szükséges.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>innerOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

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
- [Microsoft. Quantum. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)