---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: e2d6e5a663f8c4e101c7e2ab1346d10cade3f4e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223459"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ez a művelet azt ellenőrzi, hogy a qubits regisztere által képviselt egész szám nagyobb-e, mint egy másik egész szám, amely az eredmény XOR értékét egy kimeneti qubit alkalmazza.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Két egész szám `x` és `y` azonos méretű qubit-regiszterekben tárolva a művelet ellenőrzi, hogy megfelelnek-e a követelményeknek `x > y` . Ha az értéke TRUE (igaz), a rendszer XORed egy kimeneti qubit. Ellenkező esetben a 0 értéket XORed egy kimeneti qubit.
Más szóval ezt a műveletet az egységes $ $ \begin{align} U\ket {x} \ ket {y} \ ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)} jelképezheti.
\end{align} $ $

## <a name="input"></a>Bevitel

### <a name="x--littleendian"></a>x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A qubit-regisztráció során a rendszer a következő formában tárolja az összehasonlítási számot: `LittleEndian` .


### <a name="y--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A qubit-regisztráció során a következő formátumban tárolt értékkel összehasonlítandó második szám `LittleEndian` .


### <a name="output--qubit"></a>kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az összehasonlítási $x>y $ értékének eredményét tároló Qubit.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Hivatkozások

- Új kvantum-hullám – a carry addition Circuit Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton https://arxiv.org/abs/quant-ph/0410184