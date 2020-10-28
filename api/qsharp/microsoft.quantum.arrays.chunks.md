---
uid: Microsoft.Quantum.Arrays.Chunks
title: Adattömbök függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719465"
---
# <a name="chunks-function"></a>Adattömbök függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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