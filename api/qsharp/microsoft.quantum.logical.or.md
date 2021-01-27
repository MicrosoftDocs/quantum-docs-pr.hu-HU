---
uid: Microsoft.Quantum.Logical.Or
title: Vagy függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848464"
---
# <a name="or-function"></a>Vagy függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Két érték logikai kiválasztását adja vissza.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Az első megfontolandó érték.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

A második megfontolandó érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` vagy `b` a vagy a `true` .

## <a name="remarks"></a>Megjegyzések

Az `or` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.

Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:

```qsharp
let x = a or b;
let x = Or(a, b);
```