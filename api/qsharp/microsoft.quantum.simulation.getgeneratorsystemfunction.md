---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 7b6eabd203cecf8c64f0bff3e06f08a0bec31bf2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852775"
---
# <a name="getgeneratorsystemfunction-function"></a><span data-ttu-id="bc7e3-102">GetGeneratorSystemFunction függvény</span><span class="sxs-lookup"><span data-stu-id="bc7e3-102">GetGeneratorSystemFunction function</span></span>

<span data-ttu-id="bc7e3-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="bc7e3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="bc7e3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc7e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc7e3-105">A függvény beolvasása a `GeneratorIndex` alkalmazásban `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="bc7e3-105">Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.</span></span>

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a><span data-ttu-id="bc7e3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bc7e3-106">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="bc7e3-107">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="bc7e3-107">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="bc7e3-108">A `GeneratorSystem` kamat.</span><span class="sxs-lookup"><span data-stu-id="bc7e3-108">The `GeneratorSystem` of interest.</span></span>



## <a name="output--int---generatorindex"></a><span data-ttu-id="bc7e3-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bc7e3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bc7e3-110">Függvény, amely indexeli `GeneratorIndex` az egyes kifejezéseket egy Hamilton.</span><span class="sxs-lookup"><span data-stu-id="bc7e3-110">An function that indexes each `GeneratorIndex` term in a Hamiltonian.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc7e3-111">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bc7e3-111">See Also</span></span>

- [<span data-ttu-id="bc7e3-112">Microsoft. Quantum. szimulációs. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="bc7e3-112">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [<span data-ttu-id="bc7e3-113">Microsoft. Quantum. szimulációs. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="bc7e3-113">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)