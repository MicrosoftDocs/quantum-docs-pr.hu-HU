---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716665"
---
# <a name="boundc-function"></a>BoundC függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.
A módosító `C` azt jelzi, hogy a tömbben lévő összes művelet ellenőrizhető.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Bevitel

### <a name="operations--t--unit-ctl"></a>műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL []

Egy adott bemeneten végrehajtandó műveletek sora.



## <a name="output--t--unit-ctl"></a>Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL

Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)