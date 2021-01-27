---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Enumerált függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848128"
---
# <a name="enumerated-function"></a>Enumerált függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Példa

A következő `for` hurkok egyenértékűek:

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```