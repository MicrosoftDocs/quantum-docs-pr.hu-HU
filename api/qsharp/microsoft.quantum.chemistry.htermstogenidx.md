---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714858"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx függvény

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag [](https://nuget.org/packages/)


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