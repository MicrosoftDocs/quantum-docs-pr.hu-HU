---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725153"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag [](https://nuget.org/packages/)


0 bites egész szám beszúrása

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Leírás

A művelet egész számot vesz igénybe, egy 0 bitet szúr be `position` , és egész számként adja vissza a frissített értéket.  Ha például egy 0 pozíciót szúr be a 2. helyen a 10-es számú (10 $ _ {10} = 1010_ $) értékbe, {2} a a 18 értéket adja vissza (18 – 18 – 5 – 5 – 5 {10} 10010_ {2} $

## <a name="input"></a>Bevitel

### <a name="position--int"></a>pozíció: [int](xref:microsoft.quantum.lang-ref.int)

Az a pozíció, amelybe a 0 beszúrt


### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)

A módosított érték



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Módosított érték