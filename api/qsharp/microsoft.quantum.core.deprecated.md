---
uid: Microsoft.Quantum.Core.Deprecated
title: Elavult felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224088"
---
# <a name="deprecated-user-defined-type"></a>Elavult felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Fordító által felismert attribútum, amely a típus vagy a meghívható elavultként való megjelölésére szolgál.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="newname--string"></a>NewName: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

A típus teljes neve vagy hívható a használatra.
Az üres karakterláncra van beállítva, ha a típus vagy a meghívható a helyettesítés nélkül elavult.