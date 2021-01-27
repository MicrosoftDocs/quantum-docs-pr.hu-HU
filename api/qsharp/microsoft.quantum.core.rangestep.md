---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853597"
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