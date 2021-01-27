---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b31ed1b3da0d5467588f4cb2e4368e68f0dbe9d5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841118"
---
# <a name="applywithinputtransformationca-operation"></a>ApplyWithInputTransformationCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="fn--u---t"></a>FN: U-> 'T

Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.


### <a name="op--t--unit--is-adj--ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Az alkalmazni kívánt művelet.


### <a name="input--u"></a>bemenet: U

A függvény bemenete.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="u"></a>' U



## <a name="example"></a>Példa

A következő hívás @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" egy olyan művelet alkalmazására szolgál, amely @"Microsoft.Quantum.Arithmetic.BigEndian" bemenetekhez van hozzárendelve egy típusú bemenethez @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)