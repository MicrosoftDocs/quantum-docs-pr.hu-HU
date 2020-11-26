---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorEvolutionSet
title: JordanWignerClusterOperatorEvolutionSet függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 0cc40e962bcd405de608d120488904e0792d0afd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214857"
---
# <a name="jordanwignerclusteroperatorevolutionset-function"></a>JordanWignerClusterOperatorEvolutionSet függvény

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


A dinamikus generátort szimulálható kapuk készlete jelöli, a JordanWigner pedig kibővíthető.

```qsharp
function JordanWignerClusterOperatorEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Kimenet: [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Egy `EvolutionSet` , az `GeneratorIndex` JordanWigner-t egy "EvolutionUnitary" képezi.