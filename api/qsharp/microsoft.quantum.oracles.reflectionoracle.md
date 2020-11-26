---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226655"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy reflexiós Oracle-t jelöl.

A reflexiós Oracle, $O $, bemenetekkel rendelkezik:

- A $ \phi $ fázis, amelyből el kell forgatni a tükrözt alterületet.
- A qubit regisztrálnia kell a megadott reflexió végrehajtásához.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL



## <a name="remarks"></a>Megjegyzések

Ez az Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ egy részleges tükröződést végez egy $ \phi $ fázissal, amely egyetlen tiszta állapotot ($ \ket{\psi} $) mutat.