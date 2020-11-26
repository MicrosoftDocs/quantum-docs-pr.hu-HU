---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191363"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy qubit-Forgások sorozatának fázisai az amplitúdó-erősítésben.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Megjegyzések

Az első paraméter a reflexiók fázisainak egy tömbje, amely egy qubit-rotációs termékként van kifejezve.
[G.H. Alacsony, I. L. A https://arxiv.org/abs/1707.05391 ...)