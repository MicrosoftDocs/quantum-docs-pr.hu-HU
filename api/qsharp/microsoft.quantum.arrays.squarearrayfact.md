---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718853"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Azt a feltételt jelöli, hogy egy kétdimenziós tömb szögletes alakzattal rendelkezik

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Leírás

Ez a függvény azt állítja be, hogy egy tömb minden sora annyi elemet tartalmaz, mint a tömbben lévő sorok (elemek).

## <a name="input"></a>Bevitel

### <a name="array--t"></a>tömb: 'T [] []

Elemek kétdimenziós tömbje


### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Egy nyomtatandó üzenet, ha a tömb nem négyzet alakú tömb



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes elemeinek típusa `array` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. RectangularArrayFact](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)