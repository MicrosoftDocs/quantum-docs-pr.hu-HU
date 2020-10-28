---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 77538984fbd7334712df423b991ef43ce31ed849
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722408"
---
# <a name="schedulelength-function"></a>ScheduleLength függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy adott mintavételi ütemterv elemeinek számát adja vissza.

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a>Bevitel

### <a name="schedule--samplingschedule"></a>Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Az a mintavételi ütemterv, amelynek a hosszát vissza kell adni.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Az adott mintavételi ütemterv elemeinek száma.