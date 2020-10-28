---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714830"
---
# <a name="isnotzero-function"></a>IsNotZero függvény

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag [](https://nuget.org/packages/)


Ellenőrzi, hogy egy `Double` szám nem körülbelül nulla-e.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Bevitel

### <a name="number--double"></a>szám: [dupla](xref:microsoft.quantum.lang-ref.double)

Ellenőrizendő szám



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Igaz értéket ad vissza `number` , ha a értéke nagyobb, mint `1e-15` .