---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: OptimizedTrotterStepOracle függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: 523a31564ae5f054fd60161f9981c43d3467f3d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842288"
---
# <a name="optimizedtrottersteporacle-function"></a>OptimizedTrotterStepOracle függvény

Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)

Csomag: [Microsoft. Quantum. Research. kémia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Az optimalizált Trotter lépés műveletet és a futtatásához szükséges paramétereket adja vissza.

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Bevitel

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

A Hamilton formátum szerint van leírva `JordanWignerEncodingData` .


### <a name="trotterstepsize--double"></a>trotterStepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

A Trotter-integrátor lépésének mérete.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

A Trotter-integrátor sorrendje.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL))

Egy rekord, ahol `Int` a: a lefoglalt qubits száma, `Double` a `1.0/trotterStepSize` művelet pedig a Trotter lépés.