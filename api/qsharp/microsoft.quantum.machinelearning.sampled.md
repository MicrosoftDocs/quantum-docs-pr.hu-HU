---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Mintául szolgáló függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: ddff72bbed6f20e8e0ceb3bfe3fc50a3da0bd2a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211627"
---
# <a name="sampled-function"></a><span data-ttu-id="bca02-102">Mintául szolgáló függvény</span><span class="sxs-lookup"><span data-stu-id="bca02-102">Sampled function</span></span>

<span data-ttu-id="bca02-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bca02-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bca02-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bca02-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="bca02-105">Egy adott tömböt használ a megadott ütemterv alapján.</span><span class="sxs-lookup"><span data-stu-id="bca02-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bca02-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bca02-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="bca02-107">Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="bca02-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="bca02-108">A mintavételi értékekben használandó ütemterv.</span><span class="sxs-lookup"><span data-stu-id="bca02-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="bca02-109">értékek: 'T []</span><span class="sxs-lookup"><span data-stu-id="bca02-109">values : 'T[]</span></span>

<span data-ttu-id="bca02-110">A mintavételhez használandó értékek tömbje.</span><span class="sxs-lookup"><span data-stu-id="bca02-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="bca02-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="bca02-111">Output : 'T[]</span></span>

<span data-ttu-id="bca02-112">Elemek tömbje az értékek közül, az adott ütemterv alapján.</span><span class="sxs-lookup"><span data-stu-id="bca02-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bca02-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bca02-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bca02-114">Nem</span><span class="sxs-lookup"><span data-stu-id="bca02-114">'T</span></span>

