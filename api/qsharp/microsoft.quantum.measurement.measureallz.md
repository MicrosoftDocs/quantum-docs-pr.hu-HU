---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711078"
---
# <a name="measureallz-operation"></a>MeasureAllZ művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag [](https://nuget.org/packages/)


Közösen méri a qubits-regisztrációt a Pauli Z alapján.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Leírás

A qubits regiszterét méri a $Z \otimes Z \otimes \cdots \otimes Z $ alapján, amely a teljes regiszter paritását jelképezi.

## <a name="input"></a>Bevitel

### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A mérendő regisztráció.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

A \otimes \cdots \otimes Z $ \otimes $Z mérésének eredménye.