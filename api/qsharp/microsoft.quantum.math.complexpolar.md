---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847350"
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