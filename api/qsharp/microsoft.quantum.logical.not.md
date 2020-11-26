---
uid: Microsoft.Quantum.Logical.Not
title: Nem működik
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197449"
---
# <a name="not-function"></a>Nem működik

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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