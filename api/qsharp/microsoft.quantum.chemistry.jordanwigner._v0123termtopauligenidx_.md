---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: fc5ad0e97374c52a90012b0ce633af8488f3ad88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215095"
---
# <a name="_v0123termtopauligenidx_-function"></a>_V0123TermToPauliGenIdx_ függvény

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


A PQRS kifejezést leíró GeneratorIndex alakítja át a (z) "GeneratorIndex []" kifejezésre a Paulis alapján

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a>Bevitel

### <a name="term--generatorindex"></a>kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` PQRS kifejezés.



## <a name="output--generatorindex"></a>Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]

A "GeneratorIndex []" kifejezés a PQRS kifejezést a Pauli kifejezésként fejezi ki.