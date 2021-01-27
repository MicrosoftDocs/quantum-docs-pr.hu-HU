---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855198"
---
# <a name="withzeroinsertedat-function"></a>WithZeroInsertedAt függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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