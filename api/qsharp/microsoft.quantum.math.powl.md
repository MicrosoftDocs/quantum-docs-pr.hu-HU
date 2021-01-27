---
uid: Microsoft.Quantum.Math.PowL
title: PowL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: f7282a3639ca87dae731e39594576aa73c4602ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857468"
---
# <a name="powl-function"></a><span data-ttu-id="0b654-102">PowL függvény</span><span class="sxs-lookup"><span data-stu-id="0b654-102">PowL function</span></span>

<span data-ttu-id="0b654-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0b654-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0b654-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b654-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b654-105">Egy megadott hatványra emelt számot ad vissza.</span><span class="sxs-lookup"><span data-stu-id="0b654-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="0b654-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0b654-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0b654-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0b654-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0b654-108">Az a szám, $a $ értéket kell kiemelni.</span><span class="sxs-lookup"><span data-stu-id="0b654-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="0b654-109">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b654-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b654-110">A Power $b $, amelyhez $a $ értéket meg kell adni.</span><span class="sxs-lookup"><span data-stu-id="0b654-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="0b654-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0b654-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0b654-112">A Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="0b654-112">The power $a^b$</span></span>