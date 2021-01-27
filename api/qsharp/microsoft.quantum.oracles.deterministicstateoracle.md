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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="cda69-102">DeterministicStateOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="cda69-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="cda69-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="cda69-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="cda69-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cda69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cda69-105">Egy Oracle-t jelöl a determinisztikus állapotának előkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cda69-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="cda69-106">Az Oracle $O $ értékre való bemenet a következő:</span><span class="sxs-lookup"><span data-stu-id="cda69-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="cda69-107">Az a regisztráció, amely a kívánt Quantum State $ \ket{\psi} \_ s $ értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="cda69-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="cda69-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cda69-108">Remarks</span></span>

<span data-ttu-id="cda69-109">Ez a $O \ket = \ket{\psi} $ által definiált Oracle a számítási alapon kiszámított $ {0} \ket {0} $ értékkel hozza létre a $ \ket{\psi} $ értékű állapotot.</span><span class="sxs-lookup"><span data-stu-id="cda69-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="cda69-110">Az első paraméter a $ \ket{\psi} $ qubit-regisztrációja.</span><span class="sxs-lookup"><span data-stu-id="cda69-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>