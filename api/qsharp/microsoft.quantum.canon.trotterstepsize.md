---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715223"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Kiszámítja a Trotter-szimulációs algoritmus rekurzív megvalósításának Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Bevitel

### <a name="order--int"></a>megrendelés: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Megjegyzések

Ez a művelet egy eltérő indexelési konvenciót használ, mint a [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). Különösen `DecomposedIntoTimeStepsCA(_, 4)` megfelel a skaláris $p _2 (\lambda) $ a Quant-pH/0508139.