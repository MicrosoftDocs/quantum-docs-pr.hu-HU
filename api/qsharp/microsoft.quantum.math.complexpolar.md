---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210981"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A poláris formában lévő összetett számot jelöli.

Egy összetett szám poláris ábrázolása $c = r e ^ {i t} $.

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="magnitude--double"></a>Nagyság: [dupla](xref:microsoft.quantum.lang-ref.double)

Az abszolút érték $r \ge $0 $c $.
### <a name="argument--double"></a>Argumentum: [Double](xref:microsoft.quantum.lang-ref.double)

A fázis $t \in \mathbb R $ $c $.