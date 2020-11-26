---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207037"
---
# <a name="embedpauli-function"></a>EmbedPauli függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy qubit Pauli-operátor és egy qubit indexe miatt egy több qubit Pauli-operátort ad vissza a megadott qubit operátorral az adott indexben és `PauliI` minden más indexben.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Bevitel

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Egy qubit Pauli-operátort kell elhelyezni a megadott helyen.


### <a name="location--int"></a>hely: [int](xref:microsoft.quantum.lang-ref.int)

Egy index, amely `output[location] == pauli` `output` a függvény kimenetét adja meg.


### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

A visszaadott tömb hossza.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

