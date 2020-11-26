---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214007"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A (Start) számú egész számok tömbjét hozza létre `arr` . lépés.. végén.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="range--range"></a>tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)

Egy `Range` `start..step..end` tömbre konvertálandó érték.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Az egész számok új tömbje, amely a által megismétlik által megismételt értékeknek felel meg `range` .