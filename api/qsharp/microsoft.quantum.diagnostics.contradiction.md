---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Ellentmondásos függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712870"
---
# <a name="contradiction-function"></a>Ellentmondásos függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


Kijelenti, hogy a klasszikus feltétel hamis.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--bool"></a>tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)

A deklarált feltétel.


### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Az üzenet azon karakterlánca, melyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel igaz.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Diagnostics. Fact](xref:Microsoft.Quantum.Diagnostics.Fact)