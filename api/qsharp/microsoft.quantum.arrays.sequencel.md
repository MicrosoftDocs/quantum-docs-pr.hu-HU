---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Szekvenciális függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220263"
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

## <a name="remarks"></a>Megjegyzések

A és a közötti különbségnek `from` `to` egy értéknek kell lennie `Int` .