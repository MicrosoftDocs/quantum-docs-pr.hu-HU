---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 477449913732950ad26adc0cdabaaaab803a20c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853284"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt állítja, hogy a klasszikus komplex szám a várt értékkel rendelkezik a 1e-10 kis tűréshatára alapján.

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--complexpolar"></a>tényleges: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

Az ellenőrizendő szám.


### <a name="expected--complexpolar"></a>várt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

A várt érték.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

