---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214279"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy kis karakterlánc miatt egy qubit Pauli-operátort ad vissza, amely egyetlen qubit Pauli-operátorok tömbje.

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>Bevitel

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A Pauli operátor a qubits-re vonatkozik, ahol `bitsApply == bits[idx]` .


### <a name="bitapply--bool"></a>bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)

a Pauli alkalmazása, ha a bit értéke ez az érték.


### <a name="bits--bool"></a>BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Logikai tömb.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>Megjegyzések

A logikai tömbnek és a kvantum-regiszternek egyenlő hosszúságú kell lennie.