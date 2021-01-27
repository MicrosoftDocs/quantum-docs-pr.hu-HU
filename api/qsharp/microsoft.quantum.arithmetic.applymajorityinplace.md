---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843730"
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

