---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: Mintául szolgáló függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854951"
---
# <a name="sampled-function"></a><span data-ttu-id="3aeb3-102">Mintául szolgáló függvény</span><span class="sxs-lookup"><span data-stu-id="3aeb3-102">Sampled function</span></span>

<span data-ttu-id="3aeb3-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3aeb3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3aeb3-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3aeb3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3aeb3-105">Egy adott tömböt használ a megadott ütemterv alapján.</span><span class="sxs-lookup"><span data-stu-id="3aeb3-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="3aeb3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3aeb3-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="3aeb3-107">Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="3aeb3-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="3aeb3-108">A mintavételi értékekben használandó ütemterv.</span><span class="sxs-lookup"><span data-stu-id="3aeb3-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="3aeb3-109">értékek: 'T []</span><span class="sxs-lookup"><span data-stu-id="3aeb3-109">values : 'T[]</span></span>

<span data-ttu-id="3aeb3-110">A mintavételhez használandó értékek tömbje.</span><span class="sxs-lookup"><span data-stu-id="3aeb3-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="3aeb3-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="3aeb3-111">Output : 'T[]</span></span>

<span data-ttu-id="3aeb3-112">Elemek tömbje az értékek közül, az adott ütemterv alapján.</span><span class="sxs-lookup"><span data-stu-id="3aeb3-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3aeb3-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3aeb3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3aeb3-114">Nem</span><span class="sxs-lookup"><span data-stu-id="3aeb3-114">'T</span></span>

