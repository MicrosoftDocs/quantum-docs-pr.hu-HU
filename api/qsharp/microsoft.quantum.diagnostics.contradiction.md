---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Ellentmondásos függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829365"
---
# <a name="contradiction-function"></a>Ellentmondásos függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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



## <a name="example"></a>Példa

A következő Q # kód a "Hello, World" kifejezést fogja kinyomtatni:

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Diagnostics. Fact](xref:Microsoft.Quantum.Diagnostics.Fact)