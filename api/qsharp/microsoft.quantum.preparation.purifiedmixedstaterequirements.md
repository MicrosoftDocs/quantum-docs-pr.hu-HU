---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229987"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azon qubits teljes számát adja vissza, amelyeket le kell osztani ahhoz, hogy alkalmazni lehessen a által visszaadott műveletet @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Bevitel

### <a name="targeterror--double"></a>targetError: [dupla](xref:microsoft.quantum.lang-ref.double)

A célként megadott hiba $ \epsilon $.


### <a name="ncoefficients--int"></a>nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)

A vegyes állapot előkészítése során megadható együtthatók száma.



## <a name="output--mixedstatepreparationrequirements"></a>Kimenet: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

Annak leírása, hogy hány qubits van szükség a teljes értékben, valamint a függvény által használt összes index-és szemetet-regisztrációhoz @"microsoft.quantum.preparation.purifiedmixedstate" .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. előkészítés. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)