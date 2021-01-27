---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842593"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy Oracle-t jelöl a determinisztikus állapotának előkészítéséhez.

Az Oracle $O $ értékre való bemenet a következő:

- Az a regisztráció, amely a kívánt Quantum State $ \ket{\psi} \_ s $ értéket fogja tárolni.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Megjegyzések

Ez a $O \ket = \ket{\psi} $ által definiált Oracle a számítási alapon kiszámított $ {0} \ket {0} $ értékkel hozza létre a $ \ket{\psi} $ értékű állapotot.
Az első paraméter a $ \ket{\psi} $ qubit-regisztrációja.