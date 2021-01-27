---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854891"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


A paraméteres és vezérelt Forgások sorozatából álló Quantum osztályozó modellt ismerteti, amely elforgatási szögek hozzárendelését, valamint a modell által felismert két osztály közötti torzítást tartalmaz.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="structure--controlledrotation"></a>Struktúra: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

A bemenetek besorolásához használt vezérelt forgatások sora.
### <a name="parameters--double"></a>Paraméterek: [Double](xref:microsoft.quantum.lang-ref.double)[]

Rotációs szögek hozzárendelése a megadott besorolási struktúrához.
### <a name="bias--double"></a>Torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)

Az osztályozó által felismert két osztály közötti torzítás.

## <a name="references"></a>Hivatkozások

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)