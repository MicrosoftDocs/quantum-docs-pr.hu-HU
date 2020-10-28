---
uid: Microsoft.Quantum.Math.PowL
title: PowL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 22c05cf85acf691490049ce9ac27a7c6b2a4899e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724747"
---
# <a name="powl-function"></a><span data-ttu-id="1b537-102">PowL függvény</span><span class="sxs-lookup"><span data-stu-id="1b537-102">PowL function</span></span>

<span data-ttu-id="1b537-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1b537-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1b537-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b537-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b537-105">Egy megadott hatványra emelt számot ad vissza.</span><span class="sxs-lookup"><span data-stu-id="1b537-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="1b537-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1b537-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1b537-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1b537-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1b537-108">Az a szám, $a $ értéket kell kiemelni.</span><span class="sxs-lookup"><span data-stu-id="1b537-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="1b537-109">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b537-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b537-110">A Power $b $, amelyhez $a $ értéket meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="1b537-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1b537-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1b537-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1b537-112">A Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="1b537-112">The power $a^b$</span></span>