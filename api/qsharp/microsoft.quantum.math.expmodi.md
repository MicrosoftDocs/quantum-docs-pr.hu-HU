---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723361"
---
# <a name="expmodi-function"></a>ExpModI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Egy adott hatványra kiváltott egész számot ad vissza egy adott modulusra vonatkozóan.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Leírás

A expBase $x $, a Power by $p $ és a modulus $N $ értéket jelöli.
A függvény a $x ^ p \operatorname{mod} N $ értéket adja vissza.

Feltételezzük, hogy $N $, $x $ értéke pozitív, és a teljesítmény nem negatív.

## <a name="input"></a>Bevitel

### <a name="expbase--int"></a>expBase: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Megjegyzések

Időt vesz igénybe a bitek számával `power` , nem pedig `power` magával.