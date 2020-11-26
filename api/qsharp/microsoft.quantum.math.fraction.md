---
uid: Microsoft.Quantum.Math.Fraction
title: A felhasználó által megadott típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210675"
---
# <a name="fraction-user-defined-type"></a>A felhasználó által megadott típus

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az űrlap racionális számát jelöli `p/q` . Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="numerator--int"></a>Számláló: [int](xref:microsoft.quantum.lang-ref.int)

A frakció számlálója.
### <a name="denominator--int"></a>Nevező: [int](xref:microsoft.quantum.lang-ref.int)

A frakció nevezője/