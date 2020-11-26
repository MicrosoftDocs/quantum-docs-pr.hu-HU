---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216948"
---
# <a name="bounda-function"></a>Bounda függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.
A módosító `A` azt jelzi, hogy a tömbben lévő összes művelet adjointable.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Bevitel

### <a name="operations--t--unit--is-adj"></a>műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit)  []

Egy adott bemeneten végrehajtandó műveletek sora.



## <a name="output--t--unit--is-adj"></a>Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)

Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)