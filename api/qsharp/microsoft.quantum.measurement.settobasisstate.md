---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854624"
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