---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710994"
---
# <a name="obliviousoracle-user-defined-type"></a>ObliviousOracle-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag [](https://nuget.org/packages/)


Egy Oracle for feledékenys amplitúdó-erősítést jelöl.

Az Oracle $O $ bemenetei a következők:

- A Ancilla regisztrálja $a $-t, amely $O $ műveleteket végez.
- A rendszer regisztrálja $s $ értéket, amelyre a kívánt egységes $U $ alkalmazás van alkalmazva, majd a Register $a $ bejegyzés után a $ \ket{t} $ értékű állapotban van \_ .

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Megjegyzések

Ez az Oracle által definiált $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ a Ancilla State $ \ket{s} a \_ $ értékkel valósítja meg az egységes $U $ \_ - \_ t a $ \ket{\psi} $ \lambda
Az első paraméter a $ \ket{s} $ qubit regisztrálása \_ . A második paraméter a $ \ket{\psi} s $ qubit-regisztrációja \_ .