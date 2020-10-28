---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713137"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


Változó megismétlése egy Descartes-alapú terméken [0, határ [0]-1] × [0, határ: [1]-1] × [0, határ [hossz (határ) – 1]-1] és az op (ARR) meghívása a Descartes termék minden eleméhez

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="length--int"></a>Hossz: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

