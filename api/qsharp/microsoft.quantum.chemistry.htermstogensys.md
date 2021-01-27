---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851766"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys függvény

Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Adatformátumba konvertál egy Hamilton `HTerm[]` egy GeneratorSystem.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Bevitel

### <a name="data--hterm"></a>adatkezelés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Bemeneti adatok `HTerm[]` formátumban.


### <a name="termtype--int"></a>Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]

További információ a GeneratorIndex-hez.



## <a name="output--generatorsystem"></a>Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A bemenet által reprezentált Hamilton jelképező GeneratorSystem `data` .