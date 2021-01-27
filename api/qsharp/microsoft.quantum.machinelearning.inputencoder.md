---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852942"
---
# <a name="inputencoder-function"></a>InputEncoder függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Az együtthatók és a tűréshatárok halmaza egy állapot-előkészítési műveletet ad vissza, amely az egyes együtthatókat a számítási állapot megfelelő amplitúdójának megfelelően készíti elő.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Bevitel

### <a name="coefficients--double"></a>együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]

A bemeneti állapotba kódolható együtthatók.



## <a name="output--stategenerator"></a>Kimenet: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Állapot-előkészítési művelet, amely előkészíti az adott együtthatókat bemeneti állapotként egy adott regisztráción.