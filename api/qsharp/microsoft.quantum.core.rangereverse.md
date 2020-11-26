---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213837"
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