---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 97068f12050317a9aa17c95f33650ef6f406066d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723192"
---
# <a name="bitsizel-function"></a><span data-ttu-id="ed406-102">BitSizeL függvény</span><span class="sxs-lookup"><span data-stu-id="ed406-102">BitSizeL function</span></span>

<span data-ttu-id="ed406-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ed406-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ed406-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed406-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed406-105">A nem negatív egész szám esetén `a` a a jelölőhöz szükséges bitek számát adja vissza `a` .</span><span class="sxs-lookup"><span data-stu-id="ed406-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="ed406-106">Vagyis a legkisebb $n $ értéket adja vissza, amely $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="ed406-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="ed406-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ed406-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="ed406-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ed406-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ed406-109">Az egész szám, amelynek a méretét ki kell számítani.</span><span class="sxs-lookup"><span data-stu-id="ed406-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="ed406-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed406-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed406-111">A kis méret `a` .</span><span class="sxs-lookup"><span data-stu-id="ed406-111">The bit-size of `a`.</span></span>