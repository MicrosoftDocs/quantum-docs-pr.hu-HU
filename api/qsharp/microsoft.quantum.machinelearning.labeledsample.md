---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711331"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy minta, amely egy olyan osztállyal van megjelölve, amelyhez ez a minta tartozik.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="features--double"></a>Szolgáltatások: [Double](xref:microsoft.quantum.lang-ref.double)[]

Az adott minta funkcióinak vektora.
### <a name="label--int"></a>Címke: [int](xref:microsoft.quantum.lang-ref.int)

Egy egész szám felirat ahhoz az osztályhoz, amelyhez ez a minta tartozik.