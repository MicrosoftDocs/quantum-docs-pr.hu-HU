---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 1d62d25a3d04c431440cf8fc1eb585cac2c73f2e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712660"
---
# <a name="nearequalityfactcp-function"></a>NearEqualityFactCP függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


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

