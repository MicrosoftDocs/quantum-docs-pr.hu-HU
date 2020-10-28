---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724564"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="8db9d-102">GeneratorSystem-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="8db9d-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="8db9d-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="8db9d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="8db9d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8db9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8db9d-105">Az es gyűjteményét jelöli `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="8db9d-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="8db9d-106">Ezt a gyűjteményt egy Egyindexes egész szám használatával ismétli meg, és a gyűjtemény mérete feltételezhető, hogy ismert.</span><span class="sxs-lookup"><span data-stu-id="8db9d-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="8db9d-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8db9d-107">Remarks</span></span>

<span data-ttu-id="8db9d-108">A-példányok `GeneratorSystem` egyszerűen meghatározhatók a <xref:microsoft.quantum.arrays.lookupfunction> függvény használatával.</span><span class="sxs-lookup"><span data-stu-id="8db9d-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8db9d-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8db9d-109">See Also</span></span>

- [<span data-ttu-id="8db9d-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="8db9d-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)