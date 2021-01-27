---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843964"
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