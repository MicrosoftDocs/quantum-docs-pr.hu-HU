---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223527"
---
# <a name="comparegreaterthanfxp-operation"></a>CompareGreaterThanFxP művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Összehasonlítja a kvantum-regiszterekben tárolt két rögzített pont számát, és az eredményhez tartozó tükrözést vezérli.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Az első rögzített pont számának összehasonlítása.


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

A második rögzített ponthoz viszonyított szám.


### <a name="result--qubit"></a>eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az összehasonlítás eredménye. Akkor lesz tükrözött, ha `fp1 > fp2` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Az aktuális implementációhoz a két rögzített pontnak azonos és azonos számú qubits kell lennie.