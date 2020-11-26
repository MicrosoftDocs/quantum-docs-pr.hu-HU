---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190734"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A qubit többségi műveletet a következő helyen alkalmazza a qubits-jegyzékben:.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ez a művelet kiszámítja a többségi függvényt helyben, 3 qubits.

Ha a kimeneti qubit $z $ és a bemeneti qubits $x $ és $y $ értékre jelöli, a művelet a következő átalakítást hajtja végre: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.

## <a name="input"></a>Bevitel

### <a name="output--qubit"></a>kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Első bemeneti qubit. Vegye figyelembe, hogy a kimenet kiszámításának helye és tárolása ebben a qubit történik.


### <a name="input--qubit"></a>bemenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Második és harmadik bemeneti qubits.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

