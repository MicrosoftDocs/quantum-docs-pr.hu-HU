---
uid: Microsoft.Quantum.Math.Fraction
title: A felhasználó által megadott típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857518"
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