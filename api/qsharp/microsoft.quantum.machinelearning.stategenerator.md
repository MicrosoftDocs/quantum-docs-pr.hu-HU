---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722395"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy olyan műveletet ismertet, amely egy adott bemenetet készít elő egy szekvenciális osztályozó számára.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="nqubits--int"></a>NQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken a kódolt bemenet definiálva van.
### <a name="prepare--littleendian--unit-adj--ctl"></a>Előkészítés: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) - => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj + CTL

Egy olyan művelet, amely előkészíti a kódolt bemenetet egy kis endian `NQubits` qubits.