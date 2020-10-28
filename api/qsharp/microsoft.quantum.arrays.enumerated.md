---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Enumerált függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719308"
---
# <a name="enumerated-function"></a>Enumerált függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


A tömbnek megfelelően egy új tömböt ad vissza, amely az eredeti tömb elemeit tartalmazza, valamint az egyes elemek indexeit.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Bevitel

### <a name="array--telement"></a>tömb: "táv []

Egy tömb, amelynek elemeit enumerálni kell.



## <a name="output--inttelement"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int), "tele) []

Egy új tömb, amely az eredeti tömb elemeit tartalmazza az indexekkel együtt.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="telement"></a>"Táv

A tömb elemeinek típusa.