---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855454"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="b6a89-102">FastHadamardTransformed függvény</span><span class="sxs-lookup"><span data-stu-id="b6a89-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="b6a89-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b6a89-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b6a89-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6a89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6a89-105">Egy logikai függvény átalakításának kiszámítása a Hadamard-ben a {-1,1} Yates metódus használatával</span><span class="sxs-lookup"><span data-stu-id="b6a89-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b6a89-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b6a89-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="b6a89-107">függvény: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b6a89-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b6a89-108">Az igazság tábla {-1,1} kódolásban</span><span class="sxs-lookup"><span data-stu-id="b6a89-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="b6a89-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b6a89-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b6a89-110">A függvény spektrális együtthatói</span><span class="sxs-lookup"><span data-stu-id="b6a89-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="b6a89-111">Példa</span><span class="sxs-lookup"><span data-stu-id="b6a89-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```