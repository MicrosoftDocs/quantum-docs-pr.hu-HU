---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709903"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Az összehasonlítási függvény egy új függvényt ad vissza, amely a lexographically összehasonlítja a két tömböt.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Bevitel

### <a name="elementcomparison--tt---bool"></a>elementComparison: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)

Egy függvény, amely összehasonlítja a két elemet `x` , `y` és visszaadja, ha a `x` értéke kisebb vagy egyenlő `y` .



## <a name="output--tt---bool"></a>Kimenet: ('T [], 'T [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

Függvény, amely összehasonlítja a két tömböt, `xs` `ys` és visszaadja, ha a `xs` `ys` lexographical sorrendje előtt vagy azzal egyenlően történik.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az összehasonlítható tömbök elemeinek típusa.

## <a name="remarks"></a>Megjegyzések

A két tömb közötti lexographic `xs` -összehasonlítást `ys` a következő eljárás határozza meg. Tegyük fel, hogy két elem `x` és `y` egyenértékű, ha `elementComparison(x, y)` `elementComparison(y, x)` mindkettő igaz.

- Mindkét tömb össze van hasonlítva az Element-by-Element értékkel, amíg az elemek első párja nem egyenértékű. Az elsőnek megfelelően megjelenő elemet tartalmazó tömb a `elementComparison` lexographical megrendelésének első lépéseként következik be.
- Ha a rendszer nem talál nem megfelelő elemeket, és egy tömb hosszabb a többinél, akkor a rövidebb tömb jelenik meg először.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. rendezve](xref:Microsoft.Quantum.Arrays.Sorted)