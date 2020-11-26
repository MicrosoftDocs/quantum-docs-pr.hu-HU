---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: d0a598497e8a8f019bbd8da7db1c6cc4d7bde017
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224275"
---
# <a name="maybebigintasint-function"></a>MaybeBigIntAsInt függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy adott nagy egész számot egy egyenértékű egész számra konvertál, ha lehetséges.
A függvény az eredményül kapott egész számot és egy logikai jelzőt ad vissza, amely igaz, és csak akkor, ha az átalakítás lehetséges.

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a>Bevitel

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--intbool"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))



## <a name="remarks"></a>Megjegyzések

További részleteket a [C# BigInteger konstruktorában](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) talál.