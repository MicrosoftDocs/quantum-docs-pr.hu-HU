---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720280"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag [](https://nuget.org/packages/)


A siker valószínűsége miatt egyetlen Bernoulli-próbaverziót ad vissza, amely igaz a megadott valószínűséggel.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Bevitel

### <a name="successprobability--double"></a>successProbability: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a valószínűség, amellyel `true` vissza kell adni.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` a valószínűséggel `successProbability` és `false` a valószínűséggel `1.0 - successProbability` .