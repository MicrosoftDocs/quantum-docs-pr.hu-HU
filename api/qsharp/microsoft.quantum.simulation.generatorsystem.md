---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724564"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Az es gyűjteményét jelöli `GeneratorIndex` .

Ezt a gyűjteményt egy Egyindexes egész szám használatával ismétli meg, és a gyűjtemény mérete feltételezhető, hogy ismert.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Megjegyzések

A-példányok `GeneratorSystem` egyszerűen meghatározhatók a <xref:microsoft.quantum.arrays.lookupfunction> függvény használatával.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)