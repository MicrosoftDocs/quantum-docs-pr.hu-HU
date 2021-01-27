---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835401"
---
# <a name="measurementoperators-function"></a>MeasurementOperators függvény

Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Kiszámítja az összes olyan mérési operátort, amely egy Jordan-Wigner-kifejezés várható kiszámításához szükséges.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

A molekuláris rendszerek szimulálásához szükséges qubits száma.


### <a name="indices--int"></a>indexek: [int](xref:microsoft.quantum.lang-ref.int)[]

A qubit indexeit tartalmazó tömb, amely az egyes Pauli-operátorokat alkalmazza.


### <a name="termtype--int"></a>Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)

A Jordan-Wigner kifejezés típusa.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

A mérési operátorok tömbje (mindkettő a Pauli tömbje).