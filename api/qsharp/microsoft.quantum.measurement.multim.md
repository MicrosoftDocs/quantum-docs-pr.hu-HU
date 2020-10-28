---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711037"
---
# <a name="multim-operation"></a>MultiM művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag [](https://nuget.org/packages/)


A standard szintű egy adott tömb mindegyik qubit méri.

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>Bevitel

### <a name="targets--qubit"></a>célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A mérendő qubits tömbje.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__ []

A mérési eredmények tömbje.