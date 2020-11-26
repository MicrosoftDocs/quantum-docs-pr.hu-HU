---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195766"
---
# <a name="argcomplexpolar-function"></a>ArgComplexPolar függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy összetett számú típus fázisát adja vissza `ComplexPolar` .

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a>Bevitel

### <a name="input--complexpolar"></a>bemenet: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Komplex szám $c = r e ^ {i t} $.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

Fázis $ \text{Arg} [c] = t $.