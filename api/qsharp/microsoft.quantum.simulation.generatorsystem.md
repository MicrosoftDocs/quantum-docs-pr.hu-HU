---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225227"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az es gyűjteményét jelöli `GeneratorIndex` .

Ezt a gyűjteményt egy Egyindexes egész szám használatával ismétli meg, és a gyűjtemény mérete feltételezhető, hogy ismert.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Megjegyzések

A-példányok `GeneratorSystem` egyszerűen meghatározhatók a <xref:microsoft.quantum.arrays.lookupfunction> függvény használatával.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)