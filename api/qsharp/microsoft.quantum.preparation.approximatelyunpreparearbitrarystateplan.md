---
uid: Microsoft.Quantum.Preparation.ApproximatelyUnprepareArbitraryStatePlan
title: ApproximatelyUnprepareArbitraryStatePlan függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyUnprepareArbitraryStatePlan
qsharp.summary: Implementation step of arbitrary state preparation procedure.
ms.openlocfilehash: d506e3a8bff365f1c99d4ed1eb41d29ba3dbeb18
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842444"
---
# <a name="approximatelyunpreparearbitrarystateplan-function"></a>ApproximatelyUnprepareArbitraryStatePlan függvény

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az önkényes állapot-előkészítési eljárás megvalósítási lépése.

```qsharp
function ApproximatelyUnprepareArbitraryStatePlan (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], (rngControl : Range, idxTarget : Int)) : (Qubit[] => Unit is Adj + Ctl)[]
```


## <a name="input"></a>Bevitel

### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)




### <a name="coefficients--complexpolar"></a>együtthatók: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="rngcontrol--range"></a>rngControl: [tartomány](xref:microsoft.quantum.lang-ref.range)




### <a name="idxtarget--int"></a>idxTarget: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--qubit--unit--is-adj--ctl"></a>Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL []



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. előkészítés. PrepareArbitraryState](xref:Microsoft.Quantum.Preparation.PrepareArbitraryState)
- [Microsoft. Quantum. Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)