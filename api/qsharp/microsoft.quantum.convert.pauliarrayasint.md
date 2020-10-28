---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713374"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag [](https://nuget.org/packages/)


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