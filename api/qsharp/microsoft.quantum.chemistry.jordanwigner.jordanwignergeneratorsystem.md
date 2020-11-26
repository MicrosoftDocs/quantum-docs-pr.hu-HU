---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 0f6719cfac1c50cd55da30e57b0b5c5214813f24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214721"
---
# <a name="jordanwignergeneratorsystem-function"></a>JordanWignerGeneratorSystem függvény

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


A által ismertetett Hamilton alakítja át `JWOptimizedHTerms` `GeneratorSystem` az `GeneratorIndex` ebben a fájlban meghatározott egyezményben kifejezett kifejezéssel.

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Bevitel

### <a name="data--jwoptimizedhterms"></a>adatkezelés: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

A Hamilton leírása `JWOptimizedHTerms` formátumban.



## <a name="output--generatorsystem"></a>Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A Hamilton megjelenítése mint `GeneratorSystem` .