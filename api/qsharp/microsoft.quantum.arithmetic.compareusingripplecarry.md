---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721276"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Ez a művelet azt ellenőrzi, hogy a qubits regisztere által képviselt egész szám nagyobb-e, mint egy másik egész szám, amely az eredmény XOR értékét egy kimeneti qubit alkalmazza.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
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



## <a name="references"></a>Referencia

- Új kvantum-hullám – a carry addition Circuit Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton https://arxiv.org/abs/quant-ph/0410184