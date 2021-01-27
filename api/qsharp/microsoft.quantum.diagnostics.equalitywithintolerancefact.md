---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828752"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact függvény

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt a jogcímet jelöli, amely szerint egy klasszikus lebegőpontos érték a várt értékkel rendelkezik egy adott abszolút toleranciával.

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--double"></a>tényleges: [dupla](xref:microsoft.quantum.lang-ref.double)

Az ellenőrizendő szám.


### <a name="expected--double"></a>várt érték: [Double](xref:microsoft.quantum.lang-ref.double)

A várt érték.


### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

A tényleges és a várt érték közötti különbség abszolút tűréshatára.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

