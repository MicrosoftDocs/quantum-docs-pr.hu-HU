---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203093"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="9da6d-102">FastHadamardTransformed függvény</span><span class="sxs-lookup"><span data-stu-id="9da6d-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="9da6d-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9da6d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9da6d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9da6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9da6d-105">Egy logikai függvény átalakításának kiszámítása a Hadamard-ben a {-1,1} Yates metódus használatával</span><span class="sxs-lookup"><span data-stu-id="9da6d-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="9da6d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9da6d-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="9da6d-107">függvény: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9da6d-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9da6d-108">Az igazság tábla {-1,1} kódolásban</span><span class="sxs-lookup"><span data-stu-id="9da6d-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="9da6d-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9da6d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9da6d-110">A függvény spektrális együtthatói</span><span class="sxs-lookup"><span data-stu-id="9da6d-110">Spectral coefficients of the function</span></span>