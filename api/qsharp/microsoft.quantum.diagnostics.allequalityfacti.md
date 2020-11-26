---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223884"
---
# <a name="allequalityfacti-function"></a>AllEqualityFactI függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

