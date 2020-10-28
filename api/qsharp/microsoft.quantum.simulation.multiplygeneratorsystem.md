---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720233"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Az a összes kifejezés együtthatójának szorzata `GeneratorSystem` .

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Bevitel

### <a name="multiplier--double"></a>szorzó: [dupla](xref:microsoft.quantum.lang-ref.double)

A szorzó a koefficiens alapján.


### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` megszorozva.



## <a name="output--generatorsystem"></a>Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Egy olyan `GeneratorSystem` rendszer, amely együtthatókkal nagyobb tényezőt jelent `multiplier` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)