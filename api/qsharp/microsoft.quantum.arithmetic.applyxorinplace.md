---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843472"
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

