---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715069"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


Egy iterációs (klasszikusan vezérelt) fázis-értékelési algoritmus egyszeri ismétlését hajtja végre egy egységes Oracle egész számú erejével.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Egy egész számon és egy regiszteren alapuló művelet, amely $U ^ m $-t alkalmaz az adott regiszterre, ahol a $U $ az az egységes, amelynek a fázisát meg kell becsülni, és ahol $m $ az Oracle számára adott egész számú teljesítmény.


### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)

Az adott egységes Oracle alkalmazási idejének száma.


### <a name="theta--double"></a>THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)

A vezérlő qubit fázisának megfordítására szolgáló szög, mielőtt a cél állapotba lépnek.


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Az adott egységes Oracle által elvégezett állapot regisztrálása.


### <a name="controlqubit--qubit"></a>controlQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Egy kiegészítő qubit, amely az adott Oracle alkalmazásának szabályozására szolgál.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)
