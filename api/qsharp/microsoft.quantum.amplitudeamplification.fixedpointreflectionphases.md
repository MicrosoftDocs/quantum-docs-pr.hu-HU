---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721862"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


Kiszámítja a rögzített pont amplitúdó-erősítésének részleges reflexiós fázisait.

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Bevitel

### <a name="nqueries--int"></a>nQueries: [int](xref:microsoft.quantum.lang-ref.int)

Az állapot-előkészítési Oracle-nek küldött lekérdezések száma. Páratlan egész számnak kell lennie.


### <a name="successmin--double"></a>successMin: [dupla](xref:microsoft.quantum.lang-ref.double)

A cél minimális sikerességének valószínűsége.



## <a name="output--reflectionphases"></a>Kimenet: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fázisok tömbje, amelyek felhasználhatók a rögzített pont amplitúdó-erősítési kvantum-algoritmus megvalósításában.

## <a name="references"></a>Referencia

A "rögzített pontú amplitúdó-erősítés" fázisait a lekérdezések optimális számával használjuk.

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Lásd még: "összetett kvantum-kapuk módszertana"
- A fázisok [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) a következő `RotationPhases` formátumban:.