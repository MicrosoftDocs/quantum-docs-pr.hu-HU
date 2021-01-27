---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851156"
---
# <a name="drawcategorical-operation"></a>DrawCategorical művelet

Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Véletlenszerű mintát rajzol egy probablities által meghatározott kategorikus eloszlásból.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Leírás

Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.
A nullával egyenlő tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket. Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.

## <a name="input"></a>Bevitel

### <a name="probs--double"></a>Szondák: [Double](xref:microsoft.quantum.lang-ref.double)[]

Egy lebegőpontos számokból álló tömb, amely az egyes indexek kiválasztásának valószínűségével arányos.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész szám $i $, a következő valószínűséggel: $ \Pr (i) = p_i/\ sum_i p_i $, ahol $p _i $ a $i $ th eleme `probs` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)