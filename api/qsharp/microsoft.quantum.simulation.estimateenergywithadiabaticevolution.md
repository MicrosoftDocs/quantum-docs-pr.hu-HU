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
# <a name="estimateenergywithadiabaticevolution-operation"></a>EstimateEnergyWithAdiabaticEvolution művelet

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Végrehajtja az állapot-előkészítést egy `statePrepUnitary` automatikusan lefoglalt bemeneti állapotra való alkalmazásával, majd az adiabatic állapot-előkészítést a használatával `adiabaticUnitary` , és végül a fázis becslésével, amely `qpeUnitary` az eredményül kapott állapotra vonatkozik a használatával `phaseEstAlgorithm` .

```qsharp
operation EstimateEnergyWithAdiabaticEvolution (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

A szimulációhoz használt qubits száma.


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

A kezdeti dinamikus generátor állapotának előkészítését képviselő Oracle.


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy Oracle, amely a adiabatic Evolution algoritmust jelképezi, amely az algoritmus végső állapotának megvalósítására szolgál.


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

Egy egységes operátort jelképező Oracle, $U $, amely a \delta $ \ket{\phi} $ $E és a \phi \\ , \delta t $ értékű dinamikus generátor alatt az Evolutiont jelképezi.


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm: ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Double](xref:microsoft.quantum.lang-ref.double) 

Egy művelet, amely egy adott egységes művelet fázisának becslését hajtja végre.
További részletekért lásd: [iterációs fázis becslése](/quantum/libraries/characterization#iterative-phase-estimation) .



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

A ($U $ által képviselt generátor $ \hat{\phi} $-értéke