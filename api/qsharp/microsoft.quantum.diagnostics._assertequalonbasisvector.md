---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213769"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Ellenőrzi, hogy a két művelet és az `givenU` alapul szolgáló állapot alkalmazásának eredménye azonos-e `expectedU` . Az alap állapotot a paraméter írja le `basis` .
A <xref:microsoft.quantum.extensions.fliptobasis> leírással kapcsolatos további részletekért tekintse meg a függvényt.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="basis--int"></a>alap: [int](xref:microsoft.quantum.lang-ref.int)[]

A qubit-alapú állapot-azonosító (0 <= azonosító <= 3) által meghatározott Alapállapot az egyes $n $ qubits esetében.


### <a name="givenu--qubit--unit"></a>givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

$N $ qubits műveletet kell ellenőrizni.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)

$N $ qubits-re vonatkozó hivatkozási művelet, amelyet a givenU össze kell vetni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

