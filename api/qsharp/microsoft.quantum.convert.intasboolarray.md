---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224343"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy pozitív egész szám bináris ábrázolását állítja elő a visszaadott tömb kis endian ábrázolásával.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Bevitel

### <a name="number--int"></a>szám: [int](xref:microsoft.quantum.lang-ref.int)

Egy pozitív egész szám, amelyet logikai értékek tömbje alakít át.


### <a name="bits--int"></a>BITS: [int](xref:microsoft.quantum.lang-ref.int)

A bináris ábrázolásban lévő bitek száma `number` .



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]

A logikai értékek tömbje, amely a értéket jelképezi `number` .

## <a name="remarks"></a>Megjegyzések

A bemenetnek `bits` 0 és 63 közöttinek kell lennie.
A bemenetnek `number` 0 és $2 ^ {\texttt{BITS}}-$1 között kell lennie.