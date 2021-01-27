---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: b7f4083bde84c204611ea33746ae351a3e27b946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856995"
---
# <a name="multim-operation"></a>MultiM művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A standard szintű egy adott tömb mindegyik qubit méri.

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a>Bevitel

### <a name="targets--qubit"></a>célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A mérendő qubits tömbje.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__[]

A mérési eredmények tömbje.