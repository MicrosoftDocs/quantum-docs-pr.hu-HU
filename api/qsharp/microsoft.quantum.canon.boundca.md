---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844533"
---
# <a name="boundca-function"></a>BoundCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.
A módosító `CA` azt jelzi, hogy a tömbben lévő összes művelet adjointable és ellenőrizhető.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="operations--t--unit--is-adj--ctl"></a>műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL []

Egy adott bemeneten végrehajtandó műveletek sora.



## <a name="output--t--unit--is-adj--ctl"></a>Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.

## <a name="example"></a>Példa

A következők egyenértékűek:

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

és

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)