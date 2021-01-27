---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832706"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy több qubit Pauli-operátort kódol egy egész számra, amely egy qubit Pauli-operátorok tömbje.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Legfeljebb 31 qubit Pauli-operátor tömbje.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész szám, amely egyedileg azonosítja az `paulis` alább leírtakat.

## <a name="remarks"></a>Megjegyzések

Az egyes Pauli-operátorok két bites kódolással rendelkezhetnek: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $ $

A Pauli-operátorok tömbje miatt `[P0, ..., Pn]` Ez a függvény egy olyan egész számot ad vissza, amely bináris kiterjesztéssel van ellátva, és az egyes Pauli-operátorok hozzárendeléseit nagy endian sorrendben fűzi össze `bits(Pn) ... bits(P0)` .