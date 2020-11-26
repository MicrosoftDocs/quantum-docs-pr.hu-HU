---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224377"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation függvény

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Átalakítja a függvényeket a műveletekre.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Leírás

A függvény adott funkciója olyan műveletet ad vissza, amely meghívja a függvényt, és amely nem más.

## <a name="input"></a>Bevitel

### <a name="fn--input---output"></a>FN: "input->" kimenet

Egy műveletre konvertálandó függvény.



## <a name="output--input--output"></a>Kimenet: "input =>" kimenet 

Olyan művelet, `op` amely `op(input)` azonos az `fn(input)` összes esetében `input` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="input"></a>"Bemenet

Az átalakítandó függvény bemeneti típusa.
### <a name="output"></a>"Output

Az átalakítandó függvény kimeneti típusa.

## <a name="remarks"></a>Megjegyzések

Ez különösen hasznos a függvények olyan függvényekhez vagy műveletekhez való átadásához, amelyek bemenetként egy műveletet várnak.