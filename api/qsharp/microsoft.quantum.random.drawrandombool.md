---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853693"
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

## <a name="example"></a>Példa

A következő Q # kódrészlet minták egy elfogult érmeből állnak a tükrözésre:

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```