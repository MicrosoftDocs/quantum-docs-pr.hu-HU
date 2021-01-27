---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829173"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt állítja, hogy egy összetett szám a várt értékkel rendelkezik.

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--complexpolar"></a>tényleges: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Az ellenőrizendő érték.


### <a name="expected--complexpolar"></a>várt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

A várt érték.


### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

