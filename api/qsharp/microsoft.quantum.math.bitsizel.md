---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848913"
---
# <a name="bitsizel-function"></a><span data-ttu-id="294d6-102">BitSizeL függvény</span><span class="sxs-lookup"><span data-stu-id="294d6-102">BitSizeL function</span></span>

<span data-ttu-id="294d6-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="294d6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="294d6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="294d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="294d6-105">A nem negatív egész szám esetén `a` a a jelölőhöz szükséges bitek számát adja vissza `a` .</span><span class="sxs-lookup"><span data-stu-id="294d6-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="294d6-106">Vagyis a legkisebb $n $ értéket adja vissza, amely $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="294d6-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="294d6-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="294d6-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="294d6-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="294d6-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="294d6-109">Az egész szám, amelynek a méretét ki kell számítani.</span><span class="sxs-lookup"><span data-stu-id="294d6-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="294d6-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="294d6-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="294d6-111">A kis méret `a` .</span><span class="sxs-lookup"><span data-stu-id="294d6-111">The bit-size of `a`.</span></span>