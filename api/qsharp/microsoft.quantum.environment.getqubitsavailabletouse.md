---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712577"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse művelet

Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)

Csomag [](https://nuget.org/packages/)


A jelenleg használható qubits számát adja vissza.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy utasításban lefoglalt qubits száma `using` .
Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)