---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840300"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Példa

Egy művelet miatt `op` a következő két kódrészlet egyenértékű:

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)