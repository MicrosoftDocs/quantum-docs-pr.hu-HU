---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713361"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag [](https://nuget.org/packages/)


A (Start) számú egész számok tömbjét hozza létre `arr` . lépés.. végén.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="range--range"></a>tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)

Egy `Range` `start..step..end` tömbre konvertálandó érték.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Az egész számok új tömbje, amely a által megismétlik által megismételt értékeknek felel meg `range` .