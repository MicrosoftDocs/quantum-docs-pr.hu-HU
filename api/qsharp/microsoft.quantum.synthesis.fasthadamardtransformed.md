---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725181"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="9cff2-102">FastHadamardTransformed függvény</span><span class="sxs-lookup"><span data-stu-id="9cff2-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="9cff2-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9cff2-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9cff2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cff2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cff2-105">Egy logikai függvény átalakításának kiszámítása a Hadamard-ben a {-1,1} Yates metódus használatával</span><span class="sxs-lookup"><span data-stu-id="9cff2-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="9cff2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9cff2-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="9cff2-107">függvény: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9cff2-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9cff2-108">Az igazság tábla {-1,1} kódolásban</span><span class="sxs-lookup"><span data-stu-id="9cff2-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="9cff2-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9cff2-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9cff2-110">A függvény spektrális együtthatói</span><span class="sxs-lookup"><span data-stu-id="9cff2-110">Spectral coefficients of the function</span></span>