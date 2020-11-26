---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227029"
---
# <a name="mresety-operation"></a>MResetY művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egyetlen qubit mér az Y-ben, és visszaállítja a mérést követő rögzített kezdeti állapotba.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Leírás

Egy qubit mérést hajt végre a $Y $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.

## <a name="input"></a>Bevitel

### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Egyetlen qubit kell mérni.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

A `target` Pauli $Y $ alapján történő mérés eredménye.