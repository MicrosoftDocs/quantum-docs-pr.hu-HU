---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854879"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy olyan műveletet ismertet, amely egy adott bemenetet készít elő egy szekvenciális osztályozó számára.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="nqubits--int"></a>NQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken a kódolt bemenet definiálva van.
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>Előkészítés: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy olyan művelet, amely előkészíti a kódolt bemenetet egy kis endian `NQubits` qubits.