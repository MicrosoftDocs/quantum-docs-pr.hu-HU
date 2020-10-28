---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719716"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Egy adott klasszikus egész számra vonatkozó kvantum-regisztert tükröz.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Leírás

A kvantum-regisztráció eredetileg a következő állapotban van: $ \ sum_i \ alpha_i \ket{i} $, ahol az egyes $ \ket{i} $ egy egész $i $ értéket jelképező állapot, amely az adott egész szám ($ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ értékkel rendelkező bejegyzés állapotát tükrözi.

## <a name="input"></a>Bevitel

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

A klasszikus egész szám indexeli a kiinduló állapotot.


### <a name="reg--littleendian"></a>reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ez a művelet helyben, a további kiegészítő qubits kifejezett kiosztása nélkül valósítható meg.