---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853658"
---
# <a name="rangereverse-function"></a>RangeReverse függvény

Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy új tartományt ad vissza, amely a bemeneti tartomány fordított értéke.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Bevitel

### <a name="r--range"></a>r: [tartomány](xref:microsoft.quantum.lang-ref.range)

Bemeneti tartomány.



## <a name="output--range"></a>Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)

Egy új tartomány, amely a megadott tartomány fordítottja.

## <a name="remarks"></a>Megjegyzések

Vegye figyelembe, hogy a tartomány fordított értéke nem egyszerűen `end` .. `-step` . `start` , mert a tartomány tényleges utolsó eleme nem egyezhet meg `end` .