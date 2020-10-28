---
uid: Microsoft.Quantum.Logical.Or
title: Vagy függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719980"
---
# <a name="or-function"></a>Vagy függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


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

```Q#
let x = a or b;
let x = Or(a, b);
```