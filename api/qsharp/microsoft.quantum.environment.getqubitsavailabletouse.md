---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827798"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse művelet

Névtér: [Microsoft. Quantum. environment](xref:Microsoft.Quantum.Environment)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A jelenleg használható qubits számát adja vissza.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy utasításban lefoglalt qubits száma `using` .
Ha a használt célszámítógép nem adja meg ezeket az adatokat, akkor a `-1` rendszer visszaadja.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)