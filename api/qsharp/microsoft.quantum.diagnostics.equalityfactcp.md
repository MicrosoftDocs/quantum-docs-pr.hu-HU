---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712772"
---
# <a name="equalityfactcp-function"></a>EqualityFactCP függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


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

