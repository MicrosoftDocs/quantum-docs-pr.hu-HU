---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716021"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Végrehajt egy műveletet az egész tartomány Descartes-as teljesítményében lévő minden indexnél.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Leírás

A iteratív a tartomány Descartes-as teljesítményének minden elemére alkalmazza a műveletet `0..(bound - 1)` .

## <a name="input"></a>Bevitel

### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)

Az a Descartes-érték, amelybe a tartományt `0..(bound - 1)` fel kell venni.


### <a name="bound--int"></a>kötve: [int](xref:microsoft.quantum.lang-ref.int)

A tartomány hosszának megismétlésére szolgáló tartomány specifikációja.


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

Az adott Descartes-os teljesítmény minden eleméhez meghívható művelet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)