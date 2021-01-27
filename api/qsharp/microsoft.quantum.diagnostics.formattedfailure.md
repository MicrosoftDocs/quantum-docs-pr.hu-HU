---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828280"
---
# <a name="formattedfailure-function"></a>FormattedFailure függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az értelmes hibaüzenetek sikertelen végrehajtásához használt belső függvény.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--t"></a>tényleges: nem




### <a name="expected--t"></a>várt érték: 'T




### <a name="message--string"></a>üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

Ez a függvény a szimulációs futtatókörnyezetek által emulált, így lehetővé téve a formázott ellentmondások továbbítását.