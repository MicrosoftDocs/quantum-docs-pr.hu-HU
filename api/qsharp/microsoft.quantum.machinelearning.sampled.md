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
# <a name="sampled-function"></a>Mintául szolgáló függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

