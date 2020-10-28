---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724298"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag [](https://nuget.org/packages/)


Egy Oracle-t jelöl a determinisztikus állapotának előkészítéséhez.

Az Oracle $O $ értékre való bemenet a következő:

- Az a regisztráció, amely a kívánt Quantum State $ \ket{\psi} \_ s $ értéket fogja tárolni.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Megjegyzések

Ez a $O \ket = \ket{\psi} $ által definiált Oracle a számítási alapon kiszámított $ {0} \ket {0} $ értékkel hozza létre a $ \ket{\psi} $ értékű állapotot.
Az első paraméter a $ \ket{\psi} $ qubit-regisztrációja.