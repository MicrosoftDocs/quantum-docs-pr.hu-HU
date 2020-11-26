---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: a170acf635e4e2b2150ffc208fabc9782ff837b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224173"
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