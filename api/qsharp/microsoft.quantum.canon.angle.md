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
# <a name="angle-function"></a><span data-ttu-id="e5424-102">Szög függvény</span><span class="sxs-lookup"><span data-stu-id="e5424-102">Angle function</span></span>

<span data-ttu-id="e5424-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e5424-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e5424-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5424-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5424-105">1 értéket ad vissza, ha páros számú `index` 1s és-1, ha `index` páros számú 1s van.</span><span class="sxs-lookup"><span data-stu-id="e5424-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="e5424-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e5424-106">Description</span></span>

<span data-ttu-id="e5424-107">Az érték felel meg az n-változó Rademacher-Walsh spektrumának és a függvénynek az adott hozzárendelésre vonatkozó együtthatójának, amely az elforgatás szögét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="e5424-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="e5424-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e5424-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="e5424-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5424-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5424-110">Bemeneti hozzárendelés egész számként (0 és 2 ^ n – 1 között)</span><span class="sxs-lookup"><span data-stu-id="e5424-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="e5424-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5424-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

