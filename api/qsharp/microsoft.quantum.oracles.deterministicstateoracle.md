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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="26def-102">DeterministicStateOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="26def-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="26def-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="26def-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="26def-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26def-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26def-105">Egy Oracle-t jelöl a determinisztikus állapotának előkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="26def-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="26def-106">Az Oracle $O $ értékre való bemenet a következő:</span><span class="sxs-lookup"><span data-stu-id="26def-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="26def-107">Az a regisztráció, amely a kívánt Quantum State $ \ket{\psi} \_ s $ értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="26def-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="26def-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="26def-108">Remarks</span></span>

<span data-ttu-id="26def-109">Ez a $O \ket = \ket{\psi} $ által definiált Oracle a számítási alapon kiszámított $ {0} \ket {0} $ értékkel hozza létre a $ \ket{\psi} $ értékű állapotot.</span><span class="sxs-lookup"><span data-stu-id="26def-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="26def-110">Az első paraméter a $ \ket{\psi} $ qubit-regisztrációja.</span><span class="sxs-lookup"><span data-stu-id="26def-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>