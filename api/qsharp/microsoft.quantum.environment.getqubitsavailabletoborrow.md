---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712590"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow művelet

Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)

Csomag [](https://nuget.org/packages/)


A jelenleg elérhető qubits számát adja vissza.
Ez magában foglalja a nem használt qubits; Ez magában foglalja a által visszaadott qubits `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy utasításban lefoglalt qubits száma `borrowing` .
Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)