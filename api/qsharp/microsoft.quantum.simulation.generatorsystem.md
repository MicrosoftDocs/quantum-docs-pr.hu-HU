---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225227"
---
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="4b431-102">GeneratorSystem-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="4b431-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="4b431-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4b431-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4b431-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b431-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b431-105">Az es gyűjteményét jelöli `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="4b431-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="4b431-106">Ezt a gyűjteményt egy Egyindexes egész szám használatával ismétli meg, és a gyűjtemény mérete feltételezhető, hogy ismert.</span><span class="sxs-lookup"><span data-stu-id="4b431-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="4b431-107">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4b431-107">Remarks</span></span>

<span data-ttu-id="4b431-108">A-példányok `GeneratorSystem` egyszerűen meghatározhatók a <xref:microsoft.quantum.arrays.lookupfunction> függvény használatával.</span><span class="sxs-lookup"><span data-stu-id="4b431-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b431-109">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4b431-109">See Also</span></span>

- [<span data-ttu-id="4b431-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="4b431-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)