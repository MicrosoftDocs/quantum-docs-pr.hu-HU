---
uid: Microsoft.Quantum.Canon.Angle
title: Szög függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842039"
---
# <a name="angle-function"></a>Szög függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


1 értéket ad vissza, ha páros számú `index` 1s és-1, ha `index` páros számú 1s van.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Leírás

Az érték felel meg az n-változó Rademacher-Walsh spektrumának és a függvénynek az adott hozzárendelésre vonatkozó együtthatójának, amely az elforgatás szögét határozza meg.

## <a name="input"></a>Bevitel

### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Bemeneti hozzárendelés egész számként (0 és 2 ^ n – 1 között)



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

