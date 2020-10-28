---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Mintául szolgáló függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722423"
---
# <a name="sampled-function"></a><span data-ttu-id="ea0d7-102">Mintául szolgáló függvény</span><span class="sxs-lookup"><span data-stu-id="ea0d7-102">Sampled function</span></span>

<span data-ttu-id="ea0d7-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ea0d7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ea0d7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea0d7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea0d7-105">Egy adott tömböt használ a megadott ütemterv alapján.</span><span class="sxs-lookup"><span data-stu-id="ea0d7-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ea0d7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ea0d7-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="ea0d7-107">Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="ea0d7-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="ea0d7-108">A mintavételi értékekben használandó ütemterv.</span><span class="sxs-lookup"><span data-stu-id="ea0d7-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="ea0d7-109">értékek: 'T []</span><span class="sxs-lookup"><span data-stu-id="ea0d7-109">values : 'T[]</span></span>

<span data-ttu-id="ea0d7-110">A mintavételhez használandó értékek tömbje.</span><span class="sxs-lookup"><span data-stu-id="ea0d7-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="ea0d7-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="ea0d7-111">Output : 'T[]</span></span>

<span data-ttu-id="ea0d7-112">Elemek tömbje az értékek közül, az adott ütemterv alapján.</span><span class="sxs-lookup"><span data-stu-id="ea0d7-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ea0d7-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ea0d7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea0d7-114">Nem</span><span class="sxs-lookup"><span data-stu-id="ea0d7-114">'T</span></span>

