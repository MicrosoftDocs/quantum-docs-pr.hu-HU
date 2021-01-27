---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845843"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>Hivatkozások

A "rögzített pontú amplitúdó-erősítés" fázisait a lekérdezések optimális számával használjuk.

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Lásd még: "összetett kvantum-kapuk módszertana"
- A fázisok [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) a következő `RotationPhases` formátumban:.