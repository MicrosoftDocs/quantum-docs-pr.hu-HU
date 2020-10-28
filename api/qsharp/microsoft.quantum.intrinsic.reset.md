---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Visszaállítási művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720869"
---
# <a name="reset-operation"></a>Visszaállítási művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag [](https://nuget.org/packages/)


Egyetlen qubit esetén a méri azt, és gondoskodik róla, hogy a (z) | 0 ⟩ állapotban legyen, hogy biztonságosan kiszabadítható legyen.

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az a qubit, amelynek az állapotát vissza kell állítani a $ \ket $ értékre {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

