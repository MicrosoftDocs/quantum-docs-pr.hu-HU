---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709650"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


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