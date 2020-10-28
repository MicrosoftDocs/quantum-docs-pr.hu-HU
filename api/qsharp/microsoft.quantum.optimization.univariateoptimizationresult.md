---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724326"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Csomag [](https://nuget.org/packages/)


Egy univariate függvény optimalizálásának eredményét jelöli.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="coordinate--double"></a>Koordináta: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a bemenet, amelyben az optimális érték található.
### <a name="value--double"></a>Érték: [Double](xref:microsoft.quantum.lang-ref.double)

A függvény által visszaadott érték az optimálisnál.