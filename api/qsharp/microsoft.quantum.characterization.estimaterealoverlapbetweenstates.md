---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714971"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a>EstimateRealOverlapBetweenStates művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


A két művelet, amely az egyes állapotok előkészítését végzi, az egyes műveletek által előkészített állapotok közötti átfedés valódi részét becsüli meg.

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Bevitel

### <a name="commonpreparation--qubit--unit-adj"></a>commonPreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj

Egy rögzített bemeneti állapotot előkészítő művelet.


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

A két állapot-előkészítési művelet első része, amelyet össze kell hasonlítani.


### <a name="preparation2--qubit--unit-adj--ctl"></a>preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

A két állapot-előkészítési művelet második része, amelyet össze kell hasonlítani.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken a, és az összes tevékenység szerepel `commonPreparation` `preparation1` `preparation2` .


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Az átfedések becsléséhez használni kívánt mérések száma.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Megjegyzések

Ez a művelet a Hadamard tesztet használja a $ $ \begin{align} \braket{\psi valódi részének megtalálásához | V ^ {\dagger} U | \psi} \end{align} $ $, ahol a $ \ket{\psi} $ a által előkészített állapot `commonPreparation` , $U $ a művelet egységes ábrázolása `preparation1` , és a $V $ értéknek megfelelő `preparation2` .

## <a name="references"></a>Referencia

- Aharonov *et al.* [Quant – pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. jellemzés. EstimateImagOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [Microsoft. Quantum. jellemzés. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)