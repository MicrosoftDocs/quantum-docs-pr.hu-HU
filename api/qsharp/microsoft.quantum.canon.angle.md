---
uid: Microsoft.Quantum.Canon.Angle
title: Szög függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219413"
---
# <a name="angle-function"></a><span data-ttu-id="83b05-102">Szög függvény</span><span class="sxs-lookup"><span data-stu-id="83b05-102">Angle function</span></span>

<span data-ttu-id="83b05-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="83b05-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="83b05-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83b05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83b05-105">1 értéket ad vissza, ha páros számú `index` 1s és-1, ha `index` páros számú 1s van.</span><span class="sxs-lookup"><span data-stu-id="83b05-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="83b05-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="83b05-106">Description</span></span>

<span data-ttu-id="83b05-107">Az érték felel meg az n-változó Rademacher-Walsh spektrumának és a függvénynek az adott hozzárendelésre vonatkozó együtthatójának, amely az elforgatás szögét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="83b05-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="83b05-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="83b05-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="83b05-109">index: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83b05-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83b05-110">Bemeneti hozzárendelés egész számként (0 és 2 ^ n – 1 között)</span><span class="sxs-lookup"><span data-stu-id="83b05-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="83b05-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83b05-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

