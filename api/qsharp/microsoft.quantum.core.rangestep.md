---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213803"
---
# <a name="rangestep-function"></a>RangeStep függvény

Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Azt az egész számot adja vissza, amely megadja egy tartomány következő értékének kiszámítását.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Bevitel

### <a name="range--range"></a>tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A megadott tartomány megadott lépésének értéke.

## <a name="remarks"></a>Megjegyzések

A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.