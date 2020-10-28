---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725474"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag [](https://nuget.org/packages/)


Az igazság táblázatának beállítása logikai értékek tömbje alapján a változók száma szerint

A rendszer egy új tömböt ad vissza `2^numVars` , ami valószínűleg azt igényli, hogy a méretet kibővítse `table` a `false` bejegyzésekkel, vagy csonkolja azokat az `2^numVars` elemekre.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Bevitel

### <a name="table--bool"></a>tábla: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Igazság tábla az igazság értékek tömbje


### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)

Változók száma



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Méretre igazított igazság táblázat