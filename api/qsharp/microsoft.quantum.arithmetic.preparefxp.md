---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 29ba66700db83d0786a70841c7b03843a9ae6219
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222405"
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

