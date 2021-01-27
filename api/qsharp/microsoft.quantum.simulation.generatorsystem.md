---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858408"
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