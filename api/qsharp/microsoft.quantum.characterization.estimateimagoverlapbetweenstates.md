---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: f18ce43f9e5ebada4c5cc0aeff1538ac640c7390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851869"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>EstimateImagOverlapBetweenStates művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A két művelet, amely az egyes állapotok előkészítését végzi, a megbecsüli az egyes műveletek által előkészített állapotok közötti átfedés képzeletbeli részét.

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Bevitel

### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)

Egy rögzített bemeneti állapotot előkészítő művelet.


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

A két állapot-előkészítési művelet első része, amelyet össze kell hasonlítani.


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

A két állapot-előkészítési művelet második része, amelyet össze kell hasonlítani.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken a, és az összes tevékenység szerepel `commonPreparation` `preparation1` `preparation2` .


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Az átfedések becsléséhez használni kívánt mérések száma.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Megjegyzések

Ez a művelet a Hadamard teszttel keresi a $ $ \begin{align} \braket{\psi-beli képzeletbeli részét. V ^ {\dagger} U | \psi} \end{align} $ $, ahol a $ \ket{\psi} $ a által előkészített állapot `commonPreparation` , $U $ a művelet egységes ábrázolása `preparation1` , és a $V $ értéknek megfelelő `preparation2` .

## <a name="references"></a>Hivatkozások

- Aharonov *et al.* [Quant – pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. jellemzés. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. Quantum. jellemzés. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)