---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827895"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt állítja, hogy egy klasszikus lebegőpontos érték a várt értékkel rendelkezik a 1e-10 kis tűréshatára alapján.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--double"></a>tényleges: [dupla](xref:microsoft.quantum.lang-ref.double)

Az ellenőrizendő szám.


### <a name="expected--double"></a>várt érték: [Double](xref:microsoft.quantum.lang-ref.double)

A várt érték.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ez egyenértékű a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ hardcoded-tűréssel {-10} .