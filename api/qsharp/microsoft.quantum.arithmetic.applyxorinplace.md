---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210113"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy bitenkénti műveletet alkalmaz egy klasszikus egész szám és egy olyan egész szám között, amelyet a qubits regisztere képvisel.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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

