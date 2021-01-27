---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: dd042b1282d2f5386ee0b67bf57ad4027eefd493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854910"
---
# <a name="schedulelength-function"></a><span data-ttu-id="2261d-102">ScheduleLength függvény</span><span class="sxs-lookup"><span data-stu-id="2261d-102">ScheduleLength function</span></span>

<span data-ttu-id="2261d-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2261d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2261d-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2261d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2261d-105">Egy adott mintavételi ütemterv elemeinek számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2261d-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="2261d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2261d-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="2261d-107">Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="2261d-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="2261d-108">Az a mintavételi ütemterv, amelynek a hosszát vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="2261d-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="2261d-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2261d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2261d-110">Az adott mintavételi ütemterv elemeinek száma.</span><span class="sxs-lookup"><span data-stu-id="2261d-110">The number of elements in the given sampling schedule.</span></span>