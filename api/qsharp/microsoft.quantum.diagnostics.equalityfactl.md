---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829145"
---
# <a name="equalityfactl-function"></a>EqualityFactL függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

