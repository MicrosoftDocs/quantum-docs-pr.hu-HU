---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: ApplySequentialClassifier művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 8186bc57e64a52e123bef8e3556d3385c4df7034
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851443"
---
# <a name="applysequentialclassifier-operation"></a>ApplySequentialClassifier művelet

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy szekvenciális osztályozó struktúrája és paraméterezés miatt az osztályozó a qubits egy regiszterére vonatkozik.

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)




### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Az a cél regisztrálása, amelyre az osztályozó alkalmazni kell.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

