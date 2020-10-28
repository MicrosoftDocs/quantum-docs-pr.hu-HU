---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723207"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Az űrlap racionális számát jelöli `p/q` . Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="numerator--bigint"></a>Számláló: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A frakció számlálója.
### <a name="denominator--bigint"></a>Nevező: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A frakció nevezője/