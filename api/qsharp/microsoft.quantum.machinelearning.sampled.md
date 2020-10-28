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
# <a name="sampled-function"></a>Mintául szolgáló függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy adott tömböt használ a megadott ütemterv alapján.

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="schedule--samplingschedule"></a>Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

A mintavételi értékekben használandó ütemterv.


### <a name="values--t"></a>értékek: 'T []

A mintavételhez használandó értékek tömbje.



## <a name="output--t"></a>Kimenet: 'T []

Elemek tömbje az értékek közül, az adott ütemterv alapján.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

