---
uid: Microsoft.Quantum.Logical.Not
title: Nem működik
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849075"
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

```qsharp
let x = not value;
let x = Not(value);
```