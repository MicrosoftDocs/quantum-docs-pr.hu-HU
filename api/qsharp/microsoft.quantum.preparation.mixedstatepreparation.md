---
uid: Microsoft.Quantum.Preparation.MixedStatePreparation
title: MixedStatePreparation-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparation
qsharp.summary: Represents a particular mixed state that can be prepared on an index and a garbage register.
ms.openlocfilehash: 7e5b6ca755aac19a31b7e27e32e934bb823b128e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842404"
---
# <a name="mixedstatepreparation-user-defined-type"></a>MixedStatePreparation-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott kevert állapotot jelöl, amely az indexen és a szemét-regisztráción is előkészíthető.

```qsharp

newtype MixedStatePreparation = (Requirements : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements, Norm : Double, Prepare : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="requirements--mixedstatepreparationrequirements"></a>Követelmények: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)


### <a name="norm--double"></a>Norma: [dupla](xref:microsoft.quantum.lang-ref.double)


### <a name="prepare--littleendianqubitqubit--unit--is-adj--ctl"></a>Prepare: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)