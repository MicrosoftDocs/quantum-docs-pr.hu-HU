---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719884"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="bb470-102">SumGeneratorSystems függvény</span><span class="sxs-lookup"><span data-stu-id="bb470-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="bb470-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bb470-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bb470-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb470-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb470-105">Több `GeneratorSystem` s hozzáadásával új GeneratorSystem hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="bb470-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="bb470-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bb470-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="bb470-107">generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="bb470-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="bb470-108">Egy típusú tömb `GeneratorSystem[]` .</span><span class="sxs-lookup"><span data-stu-id="bb470-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="bb470-109">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="bb470-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="bb470-110">A `GeneratorSystem` rendszer a bemeneti létrehozó rendszerek összegét jelképezi.</span><span class="sxs-lookup"><span data-stu-id="bb470-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb470-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bb470-111">See Also</span></span>

- [<span data-ttu-id="bb470-112">Microsoft. Quantum. szimulációs. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="bb470-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)