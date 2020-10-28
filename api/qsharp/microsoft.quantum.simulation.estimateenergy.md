---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: EstimateEnergy művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722058"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="a9d0b-102">EstimateEnergy művelet</span><span class="sxs-lookup"><span data-stu-id="a9d0b-102">EstimateEnergy operation</span></span>

<span data-ttu-id="a9d0b-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a9d0b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a9d0b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9d0b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9d0b-105">Végrehajtja az állapot-előkészítést, ha a (z) alkalmazással `statePrepUnitary` automatikusan lefoglalt bemeneti állapotú fázis-becslést alkalmaz `qpeUnitary` az eredményül kapott állapotra vonatkozóan `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="a9d0b-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="a9d0b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a9d0b-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="a9d0b-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9d0b-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a9d0b-108">A szimuláció végrehajtásához használt qubits száma.</span><span class="sxs-lookup"><span data-stu-id="a9d0b-108">Number of qubits used to perform simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="a9d0b-109">statePrepUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9d0b-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a9d0b-110">A kezdeti dinamikus generátor állapotának előkészítését képviselő Oracle.</span><span class="sxs-lookup"><span data-stu-id="a9d0b-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="a9d0b-111">qpeUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="a9d0b-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a9d0b-112">Egy egységes operátort jelképező Oracle, $U $, amely a \delta $ \ket{\phi} $ $E és a \phi \\ , \delta t $ értékű dinamikus generátor alatt az Evolutiont jelképezi.</span><span class="sxs-lookup"><span data-stu-id="a9d0b-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="a9d0b-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9d0b-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="a9d0b-114">Egy művelet, amely egy adott egységes művelet fázisának becslését hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="a9d0b-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="a9d0b-115">További részletekért lásd: [iterációs fázis becslése](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="a9d0b-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="a9d0b-116">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9d0b-116">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9d0b-117">A $U $ által képviselt generátor által jelentett, az alapállapotú, a \hat{\phi} $ \phi $.</span><span class="sxs-lookup"><span data-stu-id="a9d0b-117">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the ground state energy of the generator represented by $U$.</span></span>