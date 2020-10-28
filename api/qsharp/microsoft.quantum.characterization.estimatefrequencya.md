---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715068"
---
# <a name="estimatefrequencya-operation"></a>EstimateFrequencyA művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


A adjointable és a mérést követően a rendszer a `Zero` megadott számú próbaverzió elvégzésével megbecsüli a gyakoriságot, amellyel a mérték sikeres (visszaadott) értékkel rendelkezik.

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Bevitel

### <a name="preparation--qubit--unit-adj"></a>előkészítés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj

Egy adjointable művelet $P $, amely előkészít egy adott állapotot $ \rho $ értékre a bemeneti regiszterében.


### <a name="measurement--qubit--__invalidresult__"></a>mérték: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __érvénytelen <Result>__ 

Egy művelet, $M $, amely a kamat mértékét jelképezi.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken az egyes műveletek előkészítése és mérése megtörténjen.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Ennyi alkalommal kell elvégezni a mérést a kamat gyakoriságának becslése érdekében.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a gyakoriság, amellyel a $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0}) $ értéket adja vissza `Zero` , amely a nem torzítatlan binomiális kalkulátor $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $ \hat{p}, ahol a $n \_ {\uparrow} $ a `Zero` megfigyelt eredmények száma.

## <a name="remarks"></a>Megjegyzések

A adjointable műveletek esetében bizonyos feltételezések olyanok, mint például a művelet meghívása, hogy a qubits pontosan ugyanazt az állapotot hozza létre, ami lehetővé teszi a célszámítógép számára a teljesítmény optimalizálása érdekében.