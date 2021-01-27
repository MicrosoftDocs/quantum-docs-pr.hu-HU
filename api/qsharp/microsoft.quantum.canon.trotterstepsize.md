---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840075"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kiszámítja a Trotter-szimulációs algoritmus rekurzív megvalósításának Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Bevitel

### <a name="order--int"></a>megrendelés: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Megjegyzések

Ez a művelet egy eltérő indexelési konvenciót használ, mint a [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). Különösen `DecomposedIntoTimeStepsCA(_, 4)` megfelel a skaláris $p _2 (\lambda) $ a Quant-pH/0508139.