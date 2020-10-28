---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721765"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag [](https://nuget.org/packages/)


Egy qubit-Forgások sorozatának fázisai az amplitúdó-erősítésben.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Megjegyzések

Az első paraméter a reflexiók fázisainak egy tömbje, amely egy qubit-rotációs termékként van kifejezve.
[G.H. Alacsony, I. L. A https://arxiv.org/abs/1707.05391 ...)