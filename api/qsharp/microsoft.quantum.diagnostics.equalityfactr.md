---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712744"
---
# <a name="equalityfactr-function"></a>EqualityFactR függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


Azt állítja be, hogy egy klasszikus eredmény változó a várt értékkel rendelkezik.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--__invalidresult__"></a>tényleges: __érvénytelen <Result>__

Az ellenőrizendő változó.


### <a name="expected--__invalidresult__"></a>várt: __érvénytelen <Result>__

A várt érték.


### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

