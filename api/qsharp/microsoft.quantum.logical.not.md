---
uid: Microsoft.Quantum.Logical.Not
title: Nem működik
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709861"
---
# <a name="not-function"></a>Nem működik

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


Egy érték logikai tagadását adja vissza.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Bevitel

### <a name="value--bool"></a>érték: [bool](xref:microsoft.quantum.lang-ref.bool)

A megtagadni kívánt érték.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Ha és csak ha `value` van `false` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let x = not value;
let x = Not(value);
```