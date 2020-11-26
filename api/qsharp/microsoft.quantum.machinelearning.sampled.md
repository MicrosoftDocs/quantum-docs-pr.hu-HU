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

