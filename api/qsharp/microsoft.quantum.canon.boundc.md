---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841046"
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

## <a name="example"></a>Példa

A következők egyenértékűek:

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

és

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)