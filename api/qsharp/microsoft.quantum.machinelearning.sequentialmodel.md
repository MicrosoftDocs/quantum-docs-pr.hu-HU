---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722394"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


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

## <a name="references"></a>Referencia

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)