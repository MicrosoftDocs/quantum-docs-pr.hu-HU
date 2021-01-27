---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850102"
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

## <a name="example"></a>Példa

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```