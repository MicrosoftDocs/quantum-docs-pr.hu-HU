---
uid: Microsoft.Quantum.Bitwise.Parity
title: Paritás függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Parity
qsharp.summary: Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).
ms.openlocfilehash: b34ef36b0336ec1dea7fdbd878c6d695b38d623e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842130"
---
# <a name="parity-function"></a>Paritás függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy egész szám bitenkénti PARITÁSát adja vissza (1, ha a bináris ábrázolása páratlan számú vagy 0 értéket tartalmaz).

```qsharp
function Parity (a : Int) : Int
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>Példa

```qsharp
let a = 248;
let x = Parity(a); // x : Int = 1.
```