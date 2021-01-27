---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: cebd08c86ad8a3793ba7d0e9ce241d7a1ef046ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858497"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="b0879-102">MultiplyGeneratorSystem függvény</span><span class="sxs-lookup"><span data-stu-id="b0879-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="b0879-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b0879-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b0879-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0879-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0879-105">Az a összes kifejezés együtthatójának szorzata `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="b0879-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="b0879-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b0879-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="b0879-107">szorzó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b0879-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b0879-108">A szorzó a koefficiens alapján.</span><span class="sxs-lookup"><span data-stu-id="b0879-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="b0879-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b0879-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b0879-110">A `GeneratorSystem` megszorozva.</span><span class="sxs-lookup"><span data-stu-id="b0879-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="b0879-111">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b0879-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b0879-112">Egy olyan `GeneratorSystem` rendszer, amely együtthatókkal nagyobb tényezőt jelent `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="b0879-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0879-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b0879-113">See Also</span></span>

- [<span data-ttu-id="b0879-114">Microsoft. Quantum. szimulációs. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="b0879-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)