---
uid: Microsoft.Quantum.Diagnostics.Test
title: Felhasználó által definiált típus tesztelése
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 2f1b521c4ef2bf8e672ca4fe7a5f380d744300b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853255"
---
# <a name="test-user-defined-type"></a>Felhasználó által definiált típus tesztelése

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A fordító által felismert attribútum, amely egy egység tesztének megjelölésére szolgál.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="executiontarget--string"></a>ExecutionTarget: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

