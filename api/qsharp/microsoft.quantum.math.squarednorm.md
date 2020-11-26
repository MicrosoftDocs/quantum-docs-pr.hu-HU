---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227301"
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