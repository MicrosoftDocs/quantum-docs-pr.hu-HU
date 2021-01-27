---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814387"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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