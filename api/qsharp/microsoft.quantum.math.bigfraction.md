---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846904"
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