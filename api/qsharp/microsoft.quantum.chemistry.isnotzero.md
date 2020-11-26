---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204062"
---
# <a name="isnotzero-function"></a>IsNotZero függvény

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Ellenőrzi, hogy egy `Double` szám nem körülbelül nulla-e.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Bevitel

### <a name="number--double"></a>szám: [dupla](xref:microsoft.quantum.lang-ref.double)

Ellenőrizendő szám



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Igaz értéket ad vissza `number` , ha a értéke nagyobb, mint `1e-15` .