---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: a506ccb637b331a392ea75383c8bd605114af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202940"
---
# <a name="rmencoding-function"></a>RMEncoding függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1} Logikai igazság értékének kódolása

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a>Bevitel

### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Logikai érték



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

1, ha `b` hamis, ellenkező esetben – 1