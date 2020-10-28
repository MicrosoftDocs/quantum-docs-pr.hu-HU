---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723725"
---
# <a name="expmodl-function"></a>ExpModL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Egy adott hatványra kiváltott egész számot ad vissza egy adott modulusra vonatkozóan.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Leírás

A expBase $x $, a Power by $p $ és a modulus $N $ értéket jelöli.
A függvény a $x ^ p \operatorname{mod} N $ értéket adja vissza.

Feltételezzük, hogy $N $, $x $ értéke pozitív, és a teljesítmény nem negatív.

## <a name="input"></a>Bevitel

### <a name="expbase--bigint"></a>expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>Power: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Megjegyzések

Időt vesz igénybe a bitek számával `power` , nem pedig `power` magával.