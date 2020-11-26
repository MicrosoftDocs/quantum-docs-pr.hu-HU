---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229205"
---
# <a name="inttopauli-function"></a>IntToPauli függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egész szám átalakítása egyetlen qubit Pauli-operátorra.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Bevitel

### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Az a tartományon belüli egész szám `0..3` , amely a Pauli-operátorokra lesz konvertálva.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A `Pauli` által megadott operátor `[PauliI, PauliX, PauliY, PauliZ][idx]` .