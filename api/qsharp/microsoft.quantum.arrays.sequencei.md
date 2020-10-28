---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718900"
---
# <a name="sequencei-function"></a>SequenceI függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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