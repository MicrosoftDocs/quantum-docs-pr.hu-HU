---
uid: Microsoft.Quantum.Canon.Angle
title: Szög függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718492"
---
# <a name="angle-function"></a>Szög függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


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

