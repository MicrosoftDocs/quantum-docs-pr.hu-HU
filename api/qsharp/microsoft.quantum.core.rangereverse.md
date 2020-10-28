---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713234"
---
# <a name="rangereverse-function"></a>RangeReverse függvény

Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Csomag [](https://nuget.org/packages/)


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