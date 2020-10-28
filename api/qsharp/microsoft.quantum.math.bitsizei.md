---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723193"
---
# <a name="bitsizei-function"></a><span data-ttu-id="72f49-102">BitSizeI függvény</span><span class="sxs-lookup"><span data-stu-id="72f49-102">BitSizeI function</span></span>

<span data-ttu-id="72f49-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="72f49-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="72f49-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72f49-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72f49-105">A nem negatív egész szám esetén `a` a a jelölőhöz szükséges bitek számát adja vissza `a` .</span><span class="sxs-lookup"><span data-stu-id="72f49-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="72f49-106">Vagyis a legkisebb $n $ értéket adja vissza, amely $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="72f49-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="72f49-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="72f49-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="72f49-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72f49-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72f49-109">Az egész szám, amelynek a méretét ki kell számítani.</span><span class="sxs-lookup"><span data-stu-id="72f49-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="72f49-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72f49-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72f49-111">A kis méret `a` .</span><span class="sxs-lookup"><span data-stu-id="72f49-111">The bit-size of `a`.</span></span>