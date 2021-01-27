---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846176"
---
# <a name="emptyarray-function"></a>EmptyArray függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy adott típus üres tömbjét adja vissza.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Kimenet: "táv []

Az üres tömb.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="telement"></a>"Táv

A tömb elemeinek típusa.

## <a name="example"></a>Példa

```qsharp
let empty = EmptyArray<Int>();
```