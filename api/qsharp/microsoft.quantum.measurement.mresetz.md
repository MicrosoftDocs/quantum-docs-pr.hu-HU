---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853744"
---
# <a name="mresetz-operation"></a>MResetZ művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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