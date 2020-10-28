---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 642f6a0af76b3b2d0703f0377c379abf33ecee71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722772"
---
# <a name="adiabaticstateenergyunitary-operation"></a><span data-ttu-id="1052a-102">AdiabaticStateEnergyUnitary művelet</span><span class="sxs-lookup"><span data-stu-id="1052a-102">AdiabaticStateEnergyUnitary operation</span></span>

<span data-ttu-id="1052a-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1052a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1052a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1052a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1052a-105">Végrehajtja az állapot-előkészítést a `statePrepUnitary` bemeneti állapotra való alkalmazásával, majd az adiabatic állapot-előkészítést a használatával `adiabaticUnitary` , és végül a fázis becslésével az `qpeUnitary` eredményül kapott állapottal kapcsolatban `phaseEstAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="1052a-105">Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.</span></span>

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="1052a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1052a-106">Input</span></span>

### <a name="stateprepunitary--qubit--unit"></a><span data-ttu-id="1052a-107">statePrepUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1052a-107">statePrepUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1052a-108">A kezdeti dinamikus generátor állapotának előkészítését képviselő Oracle.</span><span class="sxs-lookup"><span data-stu-id="1052a-108">An oracle representing state preparation for the initial dynamical generator.</span></span>


### <a name="adiabaticunitary--qubit--unit"></a><span data-ttu-id="1052a-109">adiabaticUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1052a-109">adiabaticUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1052a-110">Egy Oracle, amely a adiabatic Evolution algoritmust jelképezi, amely az algoritmus végső állapotának megvalósítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="1052a-110">An oracle representing the adiabatic evolution algorithm to be used to implement the sweeps to the final state of the algorithm.</span></span>


### <a name="qpeunitary--qubit--unit-adj--ctl"></a><span data-ttu-id="1052a-111">qpeUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1052a-111">qpeUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="1052a-112">Egy egységes operátort jelképező Oracle, $U $, amely a \delta $ \ket{\phi} $ $E és a \phi \\ , \delta t $ értékű dinamikus generátor alatt az Evolutiont jelképezi.</span><span class="sxs-lookup"><span data-stu-id="1052a-112">An oracle representing a unitary operator $U$ representing evolution for time $\delta t$ under a dynamical generator with ground state $\ket{\phi}$ and ground state energy $E = \phi\\,\delta t$.</span></span>


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a><span data-ttu-id="1052a-113">phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1052a-113">phaseEstAlgorithm : ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double)</span></span> 

<span data-ttu-id="1052a-114">Egy művelet, amely egy adott egységes művelet fázisának becslését hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="1052a-114">An operation that performs phase estimation on a given unitary operation.</span></span>
<span data-ttu-id="1052a-115">További részletekért lásd: [iterációs fázis becslése](/quantum/libraries/characterization#iterative-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="1052a-115">See [iterative phase estimation](/quantum/libraries/characterization#iterative-phase-estimation) for more details.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1052a-116">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1052a-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1052a-117">A szimuláció végrehajtásához használandó qubits.</span><span class="sxs-lookup"><span data-stu-id="1052a-117">A register of qubits to be used to perform the simulation.</span></span>



## <a name="output--double"></a><span data-ttu-id="1052a-118">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1052a-118">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1052a-119">A ($U $ által képviselt generátor $ \hat{\phi} $-értéke</span><span class="sxs-lookup"><span data-stu-id="1052a-119">An estimate $\hat{\phi}$ of the ground state energy $\phi$ of the generator represented by $U$.</span></span>