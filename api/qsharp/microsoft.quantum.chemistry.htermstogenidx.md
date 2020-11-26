---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216013"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx függvény

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Egy index átalakítása Hamilton-kifejezésre `HTerm[]` adatformátumban egy GeneratorIndex.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Bevitel

### <a name="data--hterm"></a>adatkezelés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Bemeneti adatok `HTerm[]` formátumban.


### <a name="termtype--int"></a>Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]

További információ a GeneratorIndex-hez.


### <a name="idx--int"></a>idx: [int](xref:microsoft.quantum.lang-ref.int)

Index a Hamilton kifejezéséhez



## <a name="output--generatorindex"></a>Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

A által reprezentált Hamilton kifejezést képviselő GeneratorIndex `data[idx]` , a által hozzáadott további információkkal együtt `termType` .