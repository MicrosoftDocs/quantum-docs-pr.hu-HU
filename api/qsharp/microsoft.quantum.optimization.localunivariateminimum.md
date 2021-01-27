---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854609"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum függvény

Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy univariate függvényhez tartozó helyi minimális értéket adja vissza, amely egy aranysárga intervallumos keresés használatával történik.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Bevitel

### <a name="fn--double---double"></a>FN: [dupla](xref:microsoft.quantum.lang-ref.double) -> [dupla](xref:microsoft.quantum.lang-ref.double)

A univariate függvényt a lehető legkisebbre kell állítani.


### <a name="bounds--doubledouble"></a>korlátok: ([dupla](xref:microsoft.quantum.lang-ref.double),[dupla](xref:microsoft.quantum.lang-ref.double))

Az az időköz, amelyben a helyi minimumot meg kell találni.


### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

A függvény bemenetének pontossága.
A helyi Optima-keresés folytatódni fog, amíg az intervallum nem kisebb a tűréshatárnál.



## <a name="output--univariateoptimizationresult"></a>Kimenet: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Az adott függvény helyi Optima, amely a megadott határokon belül található.