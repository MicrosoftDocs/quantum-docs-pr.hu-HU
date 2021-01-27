---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833303"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy nem negatív egész szám bináris ábrázolását állítja elő a visszaadott tömb kis endian ábrázolásával.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Bevitel

### <a name="number--int"></a>szám: [int](xref:microsoft.quantum.lang-ref.int)

Egy nem negatív egész szám, amely logikai értékek tömbje számára lesz konvertálva.


### <a name="bits--int"></a>BITS: [int](xref:microsoft.quantum.lang-ref.int)

A bináris ábrázolásban lévő bitek száma `number` .



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]

A logikai értékek tömbje, amely a értéket jelképezi `number` .

## <a name="remarks"></a>Megjegyzések

A bemenetnek `bits` 0 és 63 közöttinek kell lennie.
A bemenetnek `number` 0 és $2 ^ {\texttt{BITS}}-$1 között kell lennie.