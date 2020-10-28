---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713151"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


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


### <a name="expectedu--qubit--unit-adj"></a>expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj

$N $ qubits-re vonatkozó hivatkozási művelet, amelyet a givenU össze kell vetni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

