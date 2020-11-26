---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230446"
---
# <a name="multiplygeneratorindex-function"></a>MultiplyGeneratorIndex függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A együtthatót szorozza meg a-ben `GeneratorIndex` .

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Bevitel

### <a name="multiplier--double"></a>szorzó: [dupla](xref:microsoft.quantum.lang-ref.double)

A szorzó a koefficiens alapján.


### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

A `GeneratorIndex` megszorozva.



## <a name="output--generatorindex"></a>Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Egy olyan `GeneratorIndex` kifejezést jelöl, amelynek a faktora `multiplier` nagyobb.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)