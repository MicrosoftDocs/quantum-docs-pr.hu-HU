---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: a5ea9a776f522e927f2f4545bd417d35bda83994
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214347"
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