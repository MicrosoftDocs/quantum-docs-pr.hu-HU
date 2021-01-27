---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853309"
---
# <a name="fact-function"></a>Fact függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Kijelenti, hogy a klasszikus feltétel igaz.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--bool"></a>tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)

A deklarált feltétel.


### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Az üzenet azon karakterlánca, amelyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel hamis.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

A következő Q # kódrészlet sikertelen lesz:

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Diagnostics. ellentmondás](xref:Microsoft.Quantum.Diagnostics.Contradiction)