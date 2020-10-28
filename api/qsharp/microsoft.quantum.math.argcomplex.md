---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723263"
---
# <a name="argcomplex-function"></a>ArgComplex függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Egy összetett számú típus fázisát adja vissza `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Bevitel

### <a name="input--complex"></a>bemenet: [összetett](xref:Microsoft.Quantum.Math.Complex)

Összetett szám $c = x + i y $.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

Fázis $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.