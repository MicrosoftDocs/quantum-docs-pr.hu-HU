---
uid: Microsoft.Quantum.Convert.Call
title: Hívási művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850198"
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