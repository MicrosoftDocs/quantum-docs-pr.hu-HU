---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196327"
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