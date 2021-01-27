---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843289"
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