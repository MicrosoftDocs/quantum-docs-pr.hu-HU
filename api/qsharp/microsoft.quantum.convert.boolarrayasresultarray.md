---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224462"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy típusra konvertál egy típust `Bool[]` `Result[]` , ahol a le `true` van képezve `One` és le `false` van képezve `Zero` .

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>Bevitel

### <a name="input--bool"></a>bemenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` a konvertáláshoz.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__[]

`Result[]`A jelölője `input` .