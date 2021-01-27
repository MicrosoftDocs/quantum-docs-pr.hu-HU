---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 220a733b94fd62cef21ab13e1cb3d3f973861506
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834414"
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