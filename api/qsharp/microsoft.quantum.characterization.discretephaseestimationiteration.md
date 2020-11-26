---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 8ce1e1a2bda6507285f055c87619a8760c891082
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204385"
---
# <a name="discretephaseestimationiteration-operation"></a><span data-ttu-id="86fc0-102">DiscretePhaseEstimationIteration művelet</span><span class="sxs-lookup"><span data-stu-id="86fc0-102">DiscretePhaseEstimationIteration operation</span></span>

<span data-ttu-id="86fc0-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="86fc0-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="86fc0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86fc0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86fc0-105">Egy iterációs (klasszikusan vezérelt) fázis-értékelési algoritmus egyszeri ismétlését hajtja végre egy egységes Oracle egész számú erejével.</span><span class="sxs-lookup"><span data-stu-id="86fc0-105">Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.</span></span>

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="86fc0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="86fc0-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="86fc0-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="86fc0-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="86fc0-108">Egy egész számon és egy regiszteren alapuló művelet, amely $U ^ m $-t alkalmaz az adott regiszterre, ahol a $U $ az az egységes, amelynek a fázisát meg kell becsülni, és ahol $m $ az Oracle számára adott egész számú teljesítmény.</span><span class="sxs-lookup"><span data-stu-id="86fc0-108">Operation acting on an integer and a register, such that $U^m$ is applied to the given register, where $U$ is the unitary whose phase is to be estimated, and where $m$ is the integer power given to the oracle</span></span>


### <a name="power--int"></a><span data-ttu-id="86fc0-109">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86fc0-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86fc0-110">Az adott egységes Oracle alkalmazási idejének száma.</span><span class="sxs-lookup"><span data-stu-id="86fc0-110">Number of times to apply the given unitary oracle.</span></span>


### <a name="theta--double"></a><span data-ttu-id="86fc0-111">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="86fc0-111">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="86fc0-112">A vezérlő qubit fázisának megfordítására szolgáló szög, mielőtt a cél állapotba lépnek.</span><span class="sxs-lookup"><span data-stu-id="86fc0-112">Angle by which to invert the phase on the control qubit before acting on the target state.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="86fc0-113">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="86fc0-113">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="86fc0-114">Az adott egységes Oracle által elvégezett állapot regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="86fc0-114">Register of state acted upon by the given unitary oracle.</span></span>


### <a name="controlqubit--qubit"></a><span data-ttu-id="86fc0-115">controlQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="86fc0-115">controlQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="86fc0-116">Egy kiegészítő qubit, amely az adott Oracle alkalmazásának szabályozására szolgál.</span><span class="sxs-lookup"><span data-stu-id="86fc0-116">An auxiliary qubit used to control the application of the given oracle.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86fc0-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86fc0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

