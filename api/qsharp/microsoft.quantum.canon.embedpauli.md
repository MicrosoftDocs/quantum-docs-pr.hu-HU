---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716202"
---
# <a name="embedpauli-function"></a>EmbedPauli függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


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

