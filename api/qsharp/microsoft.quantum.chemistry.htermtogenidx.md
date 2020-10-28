---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714831"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx függvény

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag [](https://nuget.org/packages/)


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