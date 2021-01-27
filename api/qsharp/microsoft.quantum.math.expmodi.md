---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857033"
---
# <a name="expmodi-function"></a>ExpModI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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