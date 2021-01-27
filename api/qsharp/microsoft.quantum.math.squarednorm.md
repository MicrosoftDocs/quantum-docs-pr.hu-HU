---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848218"
---
# <a name="squarednorm-function"></a>SquaredNorm függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy vektor négyzetes 2 – normáját adja vissza.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Leírás

Egy vektor négyzetes 2 – normáját adja vissza. Ez azt eredményezi, hogy a $ \vec{x} $ bemenet miatt a $ \ sum_i x_i ^ 2 $ értéket adja vissza.

## <a name="input"></a>Bevitel

### <a name="array--double"></a>tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]

Az a vektor, amelynek a négyzetes 2 normáját vissza kell adni.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

A négyzetes 2 – norm `array` .