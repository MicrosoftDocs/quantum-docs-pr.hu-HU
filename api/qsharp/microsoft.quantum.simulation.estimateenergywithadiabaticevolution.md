---
uid: Microsoft.Quantum.Simulation.EstimateEnergyWithAdiabaticEvolution
title: EstimateEnergyWithAdiabaticEvolution művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergyWithAdiabaticEvolution
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 3fdbdd83b784cdc560e3160151fdf4ba4e7115e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722059"
---
# <a name="estimateenergywithadiabaticevolution-operation"></a><span data-ttu-id="a743c-102">EstimateEnergyWithAdiabaticEvolution művelet</span><span class="sxs-lookup"><span data-stu-id="a743c-102">EstimateEnergyWithAdiabaticEvolution operation</span></span>

<span data-ttu-id="a743c-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a743c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a743c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a743c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a743c-105">Végrehajtja az állapot-előkészítést egy `statePrepUnitary` automatikusan lefoglalt bemeneti állapotra való alkalmazásával, majd az adiabatic állapot-előkészítést a használatával `adiabaticUnitary` , és végül a fázis becslésével, amely `qpeUnitary` az eredményül kapott állapotra vonatkozik a használatával `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="a743c-105">Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a><span data-ttu-id="a743c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a743c-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="a743c-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a743c-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a743c-108">A szimulációhoz használt qubits száma.</span><span class="sxs-lookup"><span data-stu-id="a743c-108">Number of qubits used for the simulation.</span></span>


### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="a743c-109">statePrepUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a743c-109">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a743c-110">A kezdeti dinamikus generátor állapotának előkészítését képviselő Oracle.</span><span class="sxs-lookup"><span data-stu-id="a743c-110">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="a743c-111">adiabaticUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a743c-111">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a743c-112">Egy Oracle, amely a adiabatic Evolution algoritmust jelképezi, amely az algoritmus végső állapotának megvalósítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="a743c-112">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="a743c-113">qpeUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="a743c-113">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a743c-114">Egy egységes operátort jelképező Oracle, $U $, amely a \delta $ \ket{\phi} $ $E és a \phi \\ , \delta t $ értékű dinamikus generátor alatt az Evolutiont jelképezi.</span><span class="sxs-lookup"><span data-stu-id="a743c-114">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="a743c-115">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a743c-115">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="a743c-116">Egy művelet, amely egy adott egységes művelet fázisának becslését hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="a743c-116">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="a743c-117">További részletekért lásd: [iterációs fázis becslése](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="a743c-117">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>



## <a name="output--double"></a><span data-ttu-id="a743c-118">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a743c-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a743c-119">A ($U $ által képviselt generátor $ \hat{\phi} $-értéke</span><span class="sxs-lookup"><span data-stu-id="a743c-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>