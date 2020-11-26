---
uid: Microsoft.Quantum.Convert.Call
title: Hívási művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214211"
---
# <a name="call-operation"></a>Hívási művelet

Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy függvényt hív meg egy megadott bemenettel.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Leírás

Az adott függvény és a függvény bemenete meghívja a függvényt, és visszaadja a kimenetét.

## <a name="input"></a>Bevitel

### <a name="fn--input---output"></a>FN: "input->" kimenet

Egy meghívható függvény.


### <a name="input--input"></a>bemenet: bemenet

A függvénynek átadandó bemenet.



## <a name="output--output"></a>Kimenet: kimenet

A hívás eredménye `fn` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="input"></a>"Bemenet


### <a name="output"></a>"Output



## <a name="remarks"></a>Megjegyzések

Ez a művelet különösen hasznos ahhoz, hogy a függvényt egy adott helyen lehessen meghívni egy műveleten belül, vagy egy olyan függvény meghívásához, amelyben a művelet várható.