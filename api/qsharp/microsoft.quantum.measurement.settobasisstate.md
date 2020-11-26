---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194151"
---
# <a name="settobasisstate-operation"></a>SetToBasisState művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A qubit egy adott számítási állapotra állítja be a qubit mérésével, és szükség esetén egy kis tükrözés alkalmazásával.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="desired--__invalidresult__"></a>kívánt: __érvénytelen <Result>__

Az az állapot, amelynek alapján a qubit be kell állítani.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az a qubit, amelynek az állapotát be kell állítani.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ennek a műveletnek a invariánsa a `M(q)` visszatérés után azonnal meghívja `SetToBasisState(result, q)` azt `result` .