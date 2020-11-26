---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207581"
---
# <a name="boundc-function"></a>BoundC függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.
A módosító `C` azt jelzi, hogy a tömbben lévő összes művelet ellenőrizhető.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Bevitel

### <a name="operations--t--unit--is-ctl"></a>műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL []

Egy adott bemeneten végrehajtandó műveletek sora.



## <a name="output--t--unit--is-ctl"></a>Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)