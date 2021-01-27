---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842250"
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