---
uid: Microsoft.Quantum.Logical.And
title: És függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720797"
---
# <a name="and-function"></a>És függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Két érték logikai együttesét adja vissza.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Az első megfontolandó érték.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

A második megfontolandó érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak akkor, ha `a` és `b` mindkettő `true` .

## <a name="remarks"></a>Megjegyzések

Az `and` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.

Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:

```Q#
let x = a and b;
let x = And(a, b);
```