---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220297"
---
# <a name="sequencei-function"></a>SequenceI függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egész számokból álló tömb beolvasása egy adott intervallumban.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="from--int"></a>innen: [int](xref:microsoft.quantum.lang-ref.int)

Az intervallum egy befogadó indítási indexe.


### <a name="to--int"></a>ide: [int](xref:microsoft.quantum.lang-ref.int)

Az az intervallum, amely nem kisebb, mint `from` .



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Számok sorozatát tartalmazó tömb,... `from` `from + 1` , `to` .