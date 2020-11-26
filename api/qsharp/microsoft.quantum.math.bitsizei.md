---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195851"
---
# <a name="bitsizei-function"></a><span data-ttu-id="6f30d-102">BitSizeI függvény</span><span class="sxs-lookup"><span data-stu-id="6f30d-102">BitSizeI function</span></span>

<span data-ttu-id="6f30d-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6f30d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6f30d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f30d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f30d-105">A nem negatív egész szám esetén `a` a a jelölőhöz szükséges bitek számát adja vissza `a` .</span><span class="sxs-lookup"><span data-stu-id="6f30d-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="6f30d-106">Vagyis a legkisebb $n $ értéket adja vissza, amely $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="6f30d-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="6f30d-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6f30d-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6f30d-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f30d-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f30d-109">Az egész szám, amelynek a méretét ki kell számítani.</span><span class="sxs-lookup"><span data-stu-id="6f30d-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="6f30d-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f30d-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f30d-111">A kis méret `a` .</span><span class="sxs-lookup"><span data-stu-id="6f30d-111">The bit-size of `a`.</span></span>