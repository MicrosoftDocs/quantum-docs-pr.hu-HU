---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713067"
---
# <a name="allequalityfacti-function"></a>AllEqualityFactI függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


Azt állítja, hogy az egész értékek két tömbje egyenlő.

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--int"></a>tényleges: [int](xref:microsoft.quantum.lang-ref.int)[]

Az a tömb, amelyet egy érdeklődési teszt esetén állít elő.


### <a name="expected--int"></a>várt: [int](xref:microsoft.quantum.lang-ref.int)[]

Az a tömb, amely egy hasznos teszt esetén várható.


### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Egy nyomtatandó üzenet, ha a tömbök nem egyenlőek.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

