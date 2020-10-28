---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721600"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


A qubit többségi műveletet a következő helyen alkalmazza a qubits-jegyzékben:.

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
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

