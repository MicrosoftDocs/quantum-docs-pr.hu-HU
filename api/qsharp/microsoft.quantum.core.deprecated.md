---
uid: Microsoft.Quantum.Core.Deprecated
title: Elavult felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713276"
---
# <a name="deprecated-user-defined-type"></a>Elavult felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Csomag [](https://nuget.org/packages/)


Fordító által felismert attribútum, amely a típus vagy a meghívható elavultként való megjelölésére szolgál.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="newname--string"></a>NewName: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

A típus teljes neve vagy hívható a használatra.
Az üres karakterláncra van beállítva, ha a típus vagy a meghívható a helyettesítés nélkül elavult.