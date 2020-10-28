---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724845"
---
# <a name="inttopauli-function"></a>IntToPauli függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Egész szám átalakítása egyetlen qubit Pauli-operátorra.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Bevitel

### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Az a tartományon belüli egész szám `0..3` , amely a Pauli-operátorokra lesz konvertálva.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A `Pauli` által megadott operátor `[PauliI, PauliX, PauliY, PauliZ][idx]` .