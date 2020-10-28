---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720533"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Az egyes együtthatók és a tűréshatárok halmaza egy állapot-előkészítési műveletet ad vissza, amely az egyes együtthatókat a számítási állapot megfelelő amplitúdójának megfelelően, a megadott tűréshatárig állítja elő.

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Bevitel

### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

A megadott együtthatók bemeneti állapotba való kódolásához használandó közelítési tűréshatár.


### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

A bemeneti állapotba kódolható együtthatók.



## <a name="output--stategenerator"></a>Kimenet: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Állapot-előkészítési művelet, amely előkészíti az adott együtthatókat bemeneti állapotként egy adott regisztráción.