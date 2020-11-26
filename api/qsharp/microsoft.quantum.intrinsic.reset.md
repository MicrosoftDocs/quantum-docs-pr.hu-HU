---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Visszaállítási művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198673"
---
# <a name="reset-operation"></a>Visszaállítási művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egyetlen qubit esetén a méri azt, és gondoskodik róla, hogy a (z) | 0 ⟩ állapotban legyen, hogy biztonságosan kiszabadítható legyen.

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az a qubit, amelynek az állapotát vissza kell állítani a $ \ket $ értékre {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

