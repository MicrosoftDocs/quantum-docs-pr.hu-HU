---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193930"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="a86c0-102">DeterministicStateOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="a86c0-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="a86c0-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a86c0-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a86c0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a86c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a86c0-105">Egy Oracle-t jelöl a determinisztikus állapotának előkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a86c0-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="a86c0-106">Az Oracle $O $ értékre való bemenet a következő:</span><span class="sxs-lookup"><span data-stu-id="a86c0-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="a86c0-107">Az a regisztráció, amely a kívánt Quantum State $ \ket{\psi} \_ s $ értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="a86c0-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="a86c0-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a86c0-108">Remarks</span></span>

<span data-ttu-id="a86c0-109">Ez a $O \ket = \ket{\psi} $ által definiált Oracle a számítási alapon kiszámított $ {0} \ket {0} $ értékkel hozza létre a $ \ket{\psi} $ értékű állapotot.</span><span class="sxs-lookup"><span data-stu-id="a86c0-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="a86c0-110">Az első paraméter a $ \ket{\psi} $ qubit-regisztrációja.</span><span class="sxs-lookup"><span data-stu-id="a86c0-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>