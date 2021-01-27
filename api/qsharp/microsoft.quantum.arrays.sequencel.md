---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Szekvenciális függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850993"
---
# <a name="sequencel-function"></a>Szekvenciális függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egész számokból álló tömb beolvasása egy adott intervallumban.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Bevitel

### <a name="from--bigint"></a>Forrás: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az intervallum egy befogadó indítási indexe.


### <a name="to--bigint"></a>ide: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az az intervallum, amely nem kisebb, mint `from` .



## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

Számok sorozatát tartalmazó tömb,... `from` `from + 1` , `to` .

## <a name="example"></a>Példa

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Megjegyzések

A és a közötti különbségnek `from` `to` egy értéknek kell lennie `Int` .