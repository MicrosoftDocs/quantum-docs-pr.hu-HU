---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223748"
---
# <a name="assertphaselessthan-operation"></a>AssertPhaseLessThan művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt állítja, hogy a `number` PhaseLittleEndian kódolása kisebb, mint `value` .

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)

`number` ennél kisebbnek kell lennie.


### <a name="number--phaselittleendian"></a>szám: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Előjel nélküli egész szám, amely a következőhöz képest: `value` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A művelet ellenőrzött verziója figyelmen kívül hagyja a vezérlőket.