---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721723"
---
# <a name="targetstatereflectionoracle-function"></a>TargetStateReflectionOracle függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


A `ReflectionOracle` megcélzott állapotot a jelző qubit egyedileg megjelölve hozza létre.

A célként megadott állapot egyetlen qubit van beállítva, és az összes többi 0: $ \ket {1} _f $.

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>Bevitel

### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Az Oracle $f $ qubit jelző index.



## <a name="output--reflectionoracle"></a>Kimenet: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

A `ReflectionOracle` , amely a $ \ket _f $ által jelölt állapotot tükrözi {1} .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)