---
uid: Microsoft.Quantum.Math.PowL
title: PowL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: b3207d1854f6b69cdb5b68d354000a0b6746c0c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228321"
---
# <a name="powl-function"></a><span data-ttu-id="59eaa-102">PowL függvény</span><span class="sxs-lookup"><span data-stu-id="59eaa-102">PowL function</span></span>

<span data-ttu-id="59eaa-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="59eaa-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="59eaa-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59eaa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59eaa-105">Egy megadott hatványra emelt számot ad vissza.</span><span class="sxs-lookup"><span data-stu-id="59eaa-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="59eaa-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="59eaa-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="59eaa-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="59eaa-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="59eaa-108">Az a szám, $a $ értéket kell kiemelni.</span><span class="sxs-lookup"><span data-stu-id="59eaa-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="59eaa-109">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59eaa-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59eaa-110">A Power $b $, amelyhez $a $ értéket meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="59eaa-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="59eaa-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="59eaa-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="59eaa-112">A Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="59eaa-112">The power $a^b$</span></span>