---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716035"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Végrehajt egy műveletet minden olyan indexnél, amely több tartomány Descartes-szorzatát tartalmazza.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Leírás

A iteratív egy műveletet alkalmaz a Descartes szorzatának minden eleméhez,... `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` , `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Bevitel

### <a name="bounds--int"></a>korlátok: [int](xref:microsoft.quantum.lang-ref.int)[]

Egy tömb, amely megadja a megismételni kívánt tartományokat, és minden tartomány egész hosszként van megadva.


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

Az adott Descartes-szorzat egyes elemeinek meghívására szolgáló művelet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)