---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721736"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases függvény

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


Kiszámítja a standard amplitúdó-erősítés részleges reflexiós fázisait.

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Bevitel

### <a name="niterations--int"></a>nIterations: [int](xref:microsoft.quantum.lang-ref.int)

Az amplitúdó-erősítési Ismétlések száma a részleges reflexiós fázisok létrehozásához.



## <a name="output--reflectionphases"></a>Kimenet: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

A részleges tükrözéseknek megadott fázisokat megvalósító művelet

## <a name="remarks"></a>Megjegyzések

Az összes fázis a $ \pi $, kivéve a kezdő állapot első tükrözését és a célként megadott állapottal kapcsolatos utolsó tükrözést, amely $0 $.