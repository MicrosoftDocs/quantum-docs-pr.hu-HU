---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854467"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az állapot előkészítésére szolgáló Oracle.

Az Oracle $O $ bemenetei a következők:

- Egy egész szám, amely indexeli a jelző qubit $f $ értéket.
- A rendszer regisztrálja $s $, amely a kívánt Quantum State $ \ket{\psi} \_ s $ értéket fogja tárolni.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Megjegyzések

Ez az Oracle által meghatározott $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ a számítás alapjául szolgáló állapot $ \ket {0} \_ {f} \ket {0} \_ s $, hogy létrehozta a cél állapot $ \ket{\psi} \_ s $ és amplitúdó $ \lambda $ értéket a $ \ket {1} \_ f $ jelöléssel.
Az első paraméter egy index a $ \ket f $ qubit-regisztrációhoz {0} \_ . A második paraméter mindkét regisztert magában foglalja.