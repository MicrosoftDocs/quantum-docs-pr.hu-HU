---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710687"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>_IdentityTimeDependentGeneratorSystem függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


A Hamilton konzisztens Generátorrendszer visszaadása `H(s) = 0` , ahol a egy `s` Schedule paraméter.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Bevitel

### <a name="schedule--double"></a>ütemterv: [dupla](xref:microsoft.quantum.lang-ref.double)

A rendszer figyelmen kívül hagyja ezt a bemenetet, és a <xref:microsoft.quantum.canon.timedependentgeneratorsystem> felhasználó által definiált típussal való konzisztencia meghatározására van beállítva.



## <a name="output--generatorsystem"></a>Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A Hamilton-$H (ok) = $0-as számú, az összes $s $-hoz való evolúciót képviselő létrehozó rendszer.