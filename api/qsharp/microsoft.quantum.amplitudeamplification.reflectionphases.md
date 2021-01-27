---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847181"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az amplitúdó-erősítésben bekövetkező részleges reflexiók sorozatából álló fázisok.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="aboutstart--double"></a>AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]

Fázisok tömbje az indítási állapottal kapcsolatos reflexióhoz.
### <a name="abouttarget--double"></a>AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]

Fázisok tömbje a cél állapotának tükrözéséhez.

## <a name="remarks"></a>Megjegyzések

Mindkét tömbnek egyenlő hosszúságú kell lennie. Vegye figyelembe, hogy sok esetben a kezdeti állapot és az utolsó fázis a megcélzott állapottal kapcsolatos első fázisa globális fázis-eltolást mutat be, és $0 $ értékre állítható be.