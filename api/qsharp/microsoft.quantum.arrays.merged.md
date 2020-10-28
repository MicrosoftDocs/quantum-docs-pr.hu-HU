---
uid: Microsoft.Quantum.Arrays.Merged
title: Egyesített függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719009"
---
# <a name="merged-function"></a>Egyesített függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


A két rendezett tömböt tartalmazó tömb egyetlen tömböt ad vissza, amely a sorrend sorrendjét egyaránt tartalmazza. Belsőleg használatos egyesítés szerint.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="comparison--tt---bool"></a>összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>balra: nem []




### <a name="right--t"></a>jobb: 'T []





## <a name="output--t"></a>Kimenet: 'T []



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

