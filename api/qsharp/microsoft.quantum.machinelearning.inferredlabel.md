---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722520"
---
# <a name="inferredlabel-function"></a>InferredLabel függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


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