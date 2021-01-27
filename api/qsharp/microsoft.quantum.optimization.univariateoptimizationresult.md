---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854571"
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