---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 9de7ca64992e0a4d73c1d00218b3eab4ab545a1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832565"
---
# <a name="resultasbool-function"></a>ResultAsBool függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy típusra konvertál egy típust `Result` `Bool` , ahol a le `One` van képezve `true` és le `Zero` van képezve `false` .

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a>Bevitel

### <a name="input--__invalidresult__"></a>bemenet: __érvénytelen <Result>__

`Result` a konvertáláshoz.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`A jelölője `input` .