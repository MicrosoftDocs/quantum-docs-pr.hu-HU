---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724999"
---
# <a name="mresetx-operation"></a>MResetX művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag [](https://nuget.org/packages/)


Egy qubit X alapon, és a mérték után visszaállítja egy rögzített kezdeti állapotba.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Leírás

Egy qubit mérést hajt végre a $X $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.

## <a name="input"></a>Bevitel

### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Egyetlen qubit kell mérni.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

A `target` Pauli $X $ alapján történő mérés eredménye.