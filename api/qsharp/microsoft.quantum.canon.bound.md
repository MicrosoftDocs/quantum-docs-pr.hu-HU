---
uid: Microsoft.Quantum.Canon.Bound
title: Kötött függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841054"
---
# <a name="bound-function"></a>Kötött függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Bevitel

### <a name="operations--t--unit-"></a>műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit) []

Egy adott bemeneten végrehajtandó műveletek sora.



## <a name="output--t--unit"></a>Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.

## <a name="example"></a>Példa

A következők egyenértékűek:

```qsharp
let bound = Bound([U, V]);
bound(x);
```

és

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. Quantum. Canon. Bounda](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. Quantum. Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)