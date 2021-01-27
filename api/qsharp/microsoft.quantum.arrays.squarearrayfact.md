---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850968"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Példa

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. RectangularArrayFact](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)