---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712758"
---
# <a name="equalityfactl-function"></a>EqualityFactL függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


Azt állítja be, hogy a klasszikus BigInt változó a várt értékkel rendelkezik.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--bigint"></a>tényleges: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az ellenőrizendő szám.


### <a name="expected--bigint"></a>várt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A várt érték.


### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

