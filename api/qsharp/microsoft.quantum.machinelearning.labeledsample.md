---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846979"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy minta, amely egy olyan osztállyal van megjelölve, amelyhez ez a minta tartozik.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="features--double"></a>Szolgáltatások: [Double](xref:microsoft.quantum.lang-ref.double)[]

Az adott minta funkcióinak vektora.
### <a name="label--int"></a>Címke: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész szám felirat ahhoz az osztályhoz, amelyhez ez a minta tartozik.