---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211083"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az űrlap racionális számát jelöli `p/q` . Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="numerator--bigint"></a>Számláló: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A frakció számlálója.
### <a name="denominator--bigint"></a>Nevező: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A frakció nevezője/