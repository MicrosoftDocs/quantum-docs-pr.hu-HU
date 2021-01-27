---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840285"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Példa

Egy művelet miatt `op` a következő két kódrészlet egyenértékű:

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)