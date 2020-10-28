---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723010"
---
# <a name="preparequbit-operation"></a>PrepareQubit művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


Előkészíti a qubit a megadott Pauli-operátor + 1 ( `Zero` ) eigenstate.
Ha az Identity operátor meg van adva, a qubit a maximálisan kevert állapotba kerül elő.

Ha a qubit kezdetben a $ \ket {0} $ állapotban van, akkor ez a művelet előkészíti a qubit egy adott Pauli-operátor $ + $1 eigenstate, vagy a esetében, `PauliI` a maximálisan kevert állapotban (lásd: <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Ha a qubit a $ \ket $-tól eltérő állapotban volt {0} , a művelet a következő kapukat alkalmazza: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` és <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="basis--pauli"></a>alap: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Egy Pauli-operátor $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Egy előkészített qubit.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

