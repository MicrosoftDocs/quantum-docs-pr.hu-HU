---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192961"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A siker valószínűsége miatt egyetlen Bernoulli-próbaverziót ad vissza, amely igaz a megadott valószínűséggel.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Bevitel

### <a name="successprobability--double"></a>successProbability: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a valószínűség, amellyel `true` vissza kell adni.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` a valószínűséggel `successProbability` és `false` a valószínűséggel `1.0 - successProbability` .