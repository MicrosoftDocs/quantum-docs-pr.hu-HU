---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713585"
---
# <a name="boolasresult-function"></a>BoolAsResult függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag [](https://nuget.org/packages/)


Egy típusra konvertál egy típust `Bool` `Result` , ahol a le `true` van képezve `One` és le `false` van képezve `Zero` .

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>Bevitel

### <a name="input--bool"></a>bemenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` a konvertáláshoz.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

`Result`A jelölője `input` .