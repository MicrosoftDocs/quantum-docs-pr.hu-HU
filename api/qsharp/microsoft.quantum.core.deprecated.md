---
uid: Microsoft.Quantum.Core.Deprecated
title: Elavult felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832082"
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