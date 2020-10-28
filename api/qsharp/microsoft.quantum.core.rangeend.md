---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713248"
---
# <a name="rangeend-function"></a>RangeEnd függvény

Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Csomag [](https://nuget.org/packages/)


A megadott tartomány meghatározott záró értékét adja vissza, amely nem feltétlenül a sorrend utolsó eleme.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Bevitel

### <a name="range--range"></a>tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A megadott tartomány megadott záró értéke.

## <a name="remarks"></a>Megjegyzések

A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.

Vegye figyelembe, hogy egy tartomány meghatározott záró értéke különbözhet a tartomány által meghatározott utolsó elemtől. például egy 0. tartományban. 2.. 5 az utolsó elem 4, a záró érték pedig 5.