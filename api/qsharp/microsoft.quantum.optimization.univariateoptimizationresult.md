---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194032"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy univariate függvény optimalizálásának eredményét jelöli.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="coordinate--double"></a>Koordináta: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a bemenet, amelyben az optimális érték található.
### <a name="value--double"></a>Érték: [Double](xref:microsoft.quantum.lang-ref.double)

A függvény által visszaadott érték az optimálisnál.