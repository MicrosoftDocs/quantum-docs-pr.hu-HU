---
uid: Microsoft.Quantum.Intrinsic.Message
title: Üzenet függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849373"
---
# <a name="message-function"></a>Üzenet függvény

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy üzenet naplózása.

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a>Bevitel

### <a name="msg--string"></a>msg: [sztring](xref:microsoft.quantum.lang-ref.string)

A jelentendő üzenet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A függvény konkrét viselkedése a szimulátortól függ, de a legtöbb esetben a rendszer a megadott üzenetet fogja írni a konzolra.