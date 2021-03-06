---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842981"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott klasszikus egész számra vonatkozó kvantum-regisztert tükröz.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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