---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722927"
---
# <a name="quantumromqubitcount-function"></a>QuantumROMQubitCount függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


A által visszaadott művelethez lefoglalt qubits teljes számát adja vissza `QuantumROM` .

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>Bevitel

### <a name="targeterror--double"></a>targetError: [dupla](xref:microsoft.quantum.lang-ref.double)

A célként megadott hiba $ \epsilon $.


### <a name="ncoeffs--int"></a>nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)

A ben megadott együtthatók száma `QuantumROM` .



## <a name="output--intintint"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int)[, int,](xref:microsoft.quantum.lang-ref.int)[int](xref:microsoft.quantum.lang-ref.int)))

## <a name="first-parameter"></a>Első paraméter

Az a `(x,(y,z))` rekord `x = y + z` , ahol a qubits teljes száma, a `y` qubits száma `LittleEndian` , valamint `z` a szemetet qubits száma.