---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857702"
---
# <a name="bitsizei-function"></a><span data-ttu-id="b5b8a-102">BitSizeI függvény</span><span class="sxs-lookup"><span data-stu-id="b5b8a-102">BitSizeI function</span></span>

<span data-ttu-id="b5b8a-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b5b8a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b5b8a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5b8a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5b8a-105">A nem negatív egész szám esetén `a` a a jelölőhöz szükséges bitek számát adja vissza `a` .</span><span class="sxs-lookup"><span data-stu-id="b5b8a-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="b5b8a-106">Vagyis a legkisebb $n $ értéket adja vissza, amely $a < 2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="b5b8a-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b5b8a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b5b8a-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b5b8a-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5b8a-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5b8a-109">Az egész szám, amelynek a méretét ki kell számítani.</span><span class="sxs-lookup"><span data-stu-id="b5b8a-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="b5b8a-110">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5b8a-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5b8a-111">A kis méret `a` .</span><span class="sxs-lookup"><span data-stu-id="b5b8a-111">The bit-size of `a`.</span></span>