---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 31ed1a170a47c77c21aa8b5c291860e422af2e3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845801"
---
# <a name="preparefxp-operation"></a>PrepareFxP művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


A kvantum rögzített pont számának inicializálása klasszikus állandó értékre.

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="constant--double"></a>állandó: [dupla](xref:microsoft.quantum.lang-ref.double)

Az állandó, amelyre inicializálni kell a kvantum rögzített pontjának számát.


### <a name="fp--fixedpoint"></a>FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

A (FixedPoint típusú) rögzített pontú szám az inicializáláshoz.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

