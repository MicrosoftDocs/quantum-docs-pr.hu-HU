---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214381"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients függvény

Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Kibővíti a Jordan-Wigner-együtthatók kompakt megjelenítését, hogy egy-az-egyhez hozzárendelést szerezzen be ezek és a Pauli-kifejezések között.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Bevitel

### <a name="coeff--double"></a>coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]

Együtthatók tömbje, ahogy az Jordan-Wigner Hamilton adatstruktúrából olvasva.


### <a name="termtype--int"></a>Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)

A Jordan-Wigner kifejezés típusa.



## <a name="output--double"></a>Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]

Az együtthatók kibontott tömbje, egy Pauli-kifejezéssel.