---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724228"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="53e56-102">StateOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="53e56-102">StateOracle user defined type</span></span>

<span data-ttu-id="53e56-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="53e56-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="53e56-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53e56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53e56-105">Az állapot előkészítésére szolgáló Oracle.</span><span class="sxs-lookup"><span data-stu-id="53e56-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="53e56-106">Az Oracle $O $ bemenetei a következők:</span><span class="sxs-lookup"><span data-stu-id="53e56-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="53e56-107">Egy egész szám, amely indexeli a jelző qubit $f $ értéket.</span><span class="sxs-lookup"><span data-stu-id="53e56-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="53e56-108">A rendszer regisztrálja $s $, amely a kívánt Quantum State $ \ket{\psi} \_ s $ értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="53e56-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="53e56-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="53e56-109">Remarks</span></span>

<span data-ttu-id="53e56-110">Ez az Oracle által meghatározott $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ a számítás alapjául szolgáló állapot $ \ket {0} \_ {f} \ket {0} \_ s $, hogy létrehozta a cél állapot $ \ket{\psi} \_ s $ és amplitúdó $ \lambda $ értéket a $ \ket {1} \_ f $ jelöléssel.</span><span class="sxs-lookup"><span data-stu-id="53e56-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="53e56-111">Az első paraméter egy index a $ \ket f $ qubit-regisztrációhoz {0} \_ .</span><span class="sxs-lookup"><span data-stu-id="53e56-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="53e56-112">A második paraméter mindkét regisztert magában foglalja.</span><span class="sxs-lookup"><span data-stu-id="53e56-112">The second parameter encompassed both registers.</span></span>