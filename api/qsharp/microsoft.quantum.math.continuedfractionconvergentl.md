---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: a02b38fedb5b0025f04e7bba86f2f998493206b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723823"
---
# <a name="continuedfractionconvergentl-function"></a>ContinuedFractionConvergentL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Megkeresi a legközelebb `fraction` lévő, kisebb vagy egyenlő nevezőből álló nevezőt `denominatorBound`

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a>Bevitel

### <a name="fraction--bigfraction"></a>frakció: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)




### <a name="denominatorbound--bigint"></a>denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigfraction"></a>Kimenet: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)

A legközelebb `fraction` álló nevező a nevezőnél kisebb vagy egyenlő `denominatorBound`