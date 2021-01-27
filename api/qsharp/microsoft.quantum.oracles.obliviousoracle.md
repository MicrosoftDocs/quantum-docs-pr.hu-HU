---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842548"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="5d6a4-102">ObliviousOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="5d6a4-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="5d6a4-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="5d6a4-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="5d6a4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d6a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d6a4-105">Egy Oracle for feledékenys amplitúdó-erősítést jelöl.</span><span class="sxs-lookup"><span data-stu-id="5d6a4-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="5d6a4-106">Az Oracle $O $ bemenetei a következők:</span><span class="sxs-lookup"><span data-stu-id="5d6a4-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="5d6a4-107">A Ancilla regisztrálja $a $-t, amely $O $ műveleteket végez.</span><span class="sxs-lookup"><span data-stu-id="5d6a4-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="5d6a4-108">A rendszer regisztrálja $s $ értéket, amelyre a kívánt egységes $U $ alkalmazás van alkalmazva, majd a Register $a $ bejegyzés után a $ \ket{t} $ értékű állapotban van \_ .</span><span class="sxs-lookup"><span data-stu-id="5d6a4-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="5d6a4-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5d6a4-109">Remarks</span></span>

<span data-ttu-id="5d6a4-110">Ez az Oracle által definiált $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ a Ancilla State $ \ket{s} a \_ $ értékkel valósítja meg az egységes $U $ \_ - \_ t a $ \ket{\psi} $ \lambda</span><span class="sxs-lookup"><span data-stu-id="5d6a4-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="5d6a4-111">Az első paraméter a $ \ket{s} $ qubit regisztrálása \_ .</span><span class="sxs-lookup"><span data-stu-id="5d6a4-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="5d6a4-112">A második paraméter a $ \ket{\psi} s $ qubit-regisztrációja \_ .</span><span class="sxs-lookup"><span data-stu-id="5d6a4-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>