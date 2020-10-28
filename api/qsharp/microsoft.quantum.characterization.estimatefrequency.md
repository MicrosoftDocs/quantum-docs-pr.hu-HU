---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715083"
---
# <a name="estimatefrequency-operation"></a>EstimateFrequency művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


Az előkészítés és a mérés miatt a rendszer a `Zero` megadott számú próbaverzió elvégzésével megbecsüli a gyakoriságot, amellyel a mérték sikeres (visszatérési).

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Bevitel

### <a name="preparation--qubit--unit"></a>előkészítés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy olyan művelet, $P $, amely előkészít egy adott állapotot a \rho $ értékre a bemeneti regiszterén.


### <a name="measurement--qubit--__invalidresult__"></a>mérték: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __érvénytelen <Result>__ 

Egy művelet, $M $, amely a kamat mértékét jelképezi.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken az egyes műveletek előkészítése és mérése megtörténjen.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Ennyi alkalommal kell elvégezni a mérést a kamat gyakoriságának becslése érdekében.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a gyakoriság, amellyel a $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0}) $ értéket adja vissza `Zero` , amely a nem torzítatlan binomiális kalkulátor $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $ \hat{p}, ahol a $n \_ {\uparrow} $ a `Zero` megfigyelt eredmények száma.

Ez különösen fontos azokon a célszámítógépeken, amelyek figyelembe veszik a fizikai korlátozásokat, így a valószínűségek nem mérhetők.