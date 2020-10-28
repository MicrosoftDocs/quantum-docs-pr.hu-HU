---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711051"
---
# <a name="mresetz-operation"></a>MResetZ művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag [](https://nuget.org/packages/)


Egy qubit a Z alapján, és visszaállítja egy rögzített kezdeti állapotba a mérést követően.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Leírás

Egy qubit mérést hajt végre a $Z $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.

## <a name="input"></a>Bevitel

### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Egyetlen qubit kell mérni.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

A `target` Pauli $Z $ alapján történő mérés eredménye.