---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713598"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag [](https://nuget.org/packages/)


Egy típusra konvertál egy típust `Bool[]` `Result[]` , ahol a le `true` van képezve `One` és le `false` van képezve `Zero` .

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>Bevitel

### <a name="input--bool"></a>bemenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` a konvertáláshoz.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__ []

`Result[]`A jelölője `input` .