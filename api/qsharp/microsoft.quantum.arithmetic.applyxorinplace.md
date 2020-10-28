---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721396"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Egy bitenkénti műveletet alkalmaz egy klasszikus egész szám és egy olyan egész szám között, amelyet a qubits regisztere képvisel.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Leírás

A `X` qubits egy kis endian-regisztráción alapuló műveleteket alkalmaz egy egész számban 1 bit alapján.

Tegyük fel `value` , hogy az a és az y legyen előjel nélküli egész szám, amely `target` `InPlaceXorLE` a következő Térkép által megadott műveletet hajtja végre: $ \ket{y}\rightarrow \ket{y\oplus a} $, ahol a $ \oplus $ a bitenkénti kizárólagos vagy operátor.

## <a name="input"></a>Bevitel

### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész szám, amelynek feltételezett értéke nem negatív.


### <a name="target--littleendian"></a>cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Olyan kvantum-regiszter, amely `value` kis endian kódolásban való tárolásra szolgál.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

