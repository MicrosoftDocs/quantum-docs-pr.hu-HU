---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856163"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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