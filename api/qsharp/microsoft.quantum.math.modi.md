---
uid: Microsoft.Quantum.Math.ModI
title: ModI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: e0d735096ce00b97ac42b336ac226e8e25879c94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195018"
---
# <a name="modi-function"></a><span data-ttu-id="d64f2-102">ModI függvény</span><span class="sxs-lookup"><span data-stu-id="d64f2-102">ModI function</span></span>

<span data-ttu-id="d64f2-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d64f2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d64f2-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d64f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d64f2-105">Egy szám modulusát adja vissza egy másik számra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="d64f2-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="d64f2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d64f2-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d64f2-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d64f2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d64f2-108">A bemeneti $a $, amelynek a modulusát vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="d64f2-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="d64f2-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d64f2-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d64f2-110">Az a szám, amelynek a $a $ értékét vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="d64f2-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="d64f2-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d64f2-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d64f2-112">A modulus $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="d64f2-112">The modulus $a \bmod b$.</span></span>