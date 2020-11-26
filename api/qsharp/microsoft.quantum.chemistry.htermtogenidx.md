---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216030"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx függvény

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Hamilton-kifejezést alakít át `HTerm` adatformátumba egy GeneratorIndex.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Bevitel

### <a name="term--hterm"></a>kifejezés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

Bemeneti adatok `HTerm` formátumban.


### <a name="termtype--int"></a>Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]

További információ a GeneratorIndex-hez.



## <a name="output--generatorindex"></a>Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

A által reprezentált Hamilton kifejezést képviselő GeneratorIndex `term` , a által hozzáadott további információkkal együtt `termType` .