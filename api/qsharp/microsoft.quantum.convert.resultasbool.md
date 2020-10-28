---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 34fca15faf79f706b398e3fdfc537ea91b28da86
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713346"
---
# <a name="resultasbool-function"></a>ResultAsBool függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag [](https://nuget.org/packages/)


Egy típusra konvertál egy típust `Result` `Bool` , ahol a le `One` van képezve `true` és le `Zero` van képezve `false` .

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a>Bevitel

### <a name="input--__invalidresult__"></a>bemenet: __érvénytelen <Result>__

`Result` a konvertáláshoz.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`A jelölője `input` .