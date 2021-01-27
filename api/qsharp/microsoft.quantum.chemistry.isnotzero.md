---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839595"
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