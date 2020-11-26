---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 5a85fd9f81cec0f2de7e7807622aab9604a4db7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214313"
---
# <a name="boolarrayasbigint-function"></a>BoolArrayAsBigInt függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Logikai értékek adott tömbjét konvertálja egy egyenértékű nagy egész számra.
A tömb 0 eleme a legkevesebb nagy egész szám.

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>Bevitel

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Megjegyzések

További részleteket a [C# BigInteger konstruktorában](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) talál.