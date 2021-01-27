---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 0e64d2b599c55c19711208670030fd01e09aff7e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851018"
---
# <a name="sumgeneratorsystems-function"></a>SumGeneratorSystems függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Több `GeneratorSystem` s hozzáadásával új GeneratorSystem hozhat létre.

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Bevitel

### <a name="generatorsystems--generatorsystem"></a>generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]

Egy típusú tömb `GeneratorSystem[]` .



## <a name="output--generatorsystem"></a>Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` rendszer a bemeneti létrehozó rendszerek összegét jelképezi.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)