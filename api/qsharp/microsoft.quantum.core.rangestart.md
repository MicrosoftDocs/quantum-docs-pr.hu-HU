---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713165"
---
# <a name="rangestart-function"></a>RangeStart függvény

Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Csomag [](https://nuget.org/packages/)


A megadott tartomány megadott indítási értékét adja vissza.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Bevitel

### <a name="range--range"></a>tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A megadott tartomány megadott indítási értéke.

## <a name="remarks"></a>Megjegyzések

A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.

Vegye figyelembe, hogy a tartomány definiált indítási értéke megegyezik a sor első elemével, kivéve, ha a tartomány üres sorozatot ad meg (például 2.. 1).