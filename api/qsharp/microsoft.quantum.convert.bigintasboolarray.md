---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 1ce83389f2ac3ce9ab2898f9d167941ca2973508
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834593"
---
# <a name="bigintasboolarray-function"></a>BigIntAsBoolArray függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy adott nagy egész számot alakít át logikai értékek tömbje számára.
A tömb 0 eleme a legkevesebb nagy egész szám.

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a>Bevitel

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]



## <a name="remarks"></a>Megjegyzések

További részleteket a [C# BigInteger konstruktorában](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) talál.