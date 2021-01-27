---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854672"
---
# <a name="measureallz-operation"></a>MeasureAllZ művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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