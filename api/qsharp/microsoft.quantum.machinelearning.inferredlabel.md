---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848417"
---
# <a name="inferredlabel-function"></a>InferredLabel függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


A besorolási valószínűség és a torzítás miatt a rendszer visszaadja az adott valószínűség alapján kikövetkeztetett címkét.

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>Bevitel

### <a name="bias--double"></a>torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)

A két osztály közötti torzítás, jellemzően az osztályozó betanításának eredménye.


### <a name="probability--double"></a>valószínűség: [dupla](xref:microsoft.quantum.lang-ref.double)

Egy adott minta besorolási valószínűsége, jellemzően a besorolás gyakoriságának becslése miatt.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A címkét a megadott besorolási valószínűség alapján következtették ki.