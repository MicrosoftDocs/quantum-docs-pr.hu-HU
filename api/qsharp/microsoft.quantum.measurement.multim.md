---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226995"
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