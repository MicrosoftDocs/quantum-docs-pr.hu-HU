---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835617"
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