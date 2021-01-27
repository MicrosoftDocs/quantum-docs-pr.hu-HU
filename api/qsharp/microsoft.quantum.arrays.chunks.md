---
uid: Microsoft.Quantum.Arrays.Chunks
title: Adattömbök függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842873"
---
# <a name="chunks-function"></a>Adattömbök függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tömb felosztása több, egyenlő hosszúságú részre.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Bevitel

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)

Az egyes adattömbök hossza.


### <a name="arr--t"></a>ARR: 'T []

A darabolni kívánt tömb.



## <a name="output--t"></a>Kimenet: 'T [] []

Az eredeti tömb minden egyes részletét tartalmazó tömb.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

Vegye figyelembe, hogy a kimenet utolsó eleme rövidebb lehet, mint `nElements` Ha a `Length(arr)` nem osztható meg `nElements` .