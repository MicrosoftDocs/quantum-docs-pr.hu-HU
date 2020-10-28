---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Szekvenciális függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718877"
---
# <a name="sequencel-function"></a>Szekvenciális függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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