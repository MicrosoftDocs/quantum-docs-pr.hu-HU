---
uid: Microsoft.Quantum.Intrinsic.Message
title: Üzenet függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199012"
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