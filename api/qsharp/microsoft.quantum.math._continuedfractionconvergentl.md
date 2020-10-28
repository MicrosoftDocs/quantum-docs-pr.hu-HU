---
uid: Microsoft.Quantum.Math._ContinuedFractionConvergentL
title: _ContinuedFractionConvergentL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ContinuedFractionConvergentL
qsharp.summary: Internal recursive call to calculate the GCD with a bound
ms.openlocfilehash: b8a7d17df9c1c7e36bfca0e529694ccf0979c2ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723403"
---
# <a name="_continuedfractionconvergentl-function"></a><span data-ttu-id="2a795-102">_ContinuedFractionConvergentL függvény</span><span class="sxs-lookup"><span data-stu-id="2a795-102">_ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="2a795-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2a795-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2a795-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a795-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a795-105">Belső rekurzív hívás a GCD kiszámításához kötött értékkel</span><span class="sxs-lookup"><span data-stu-id="2a795-105">Internal recursive call to calculate the GCD with a bound</span></span>

```qsharp
function _ContinuedFractionConvergentL (signA : Int, signB : Int, r : (BigInt, BigInt), s : (BigInt, BigInt), t : (BigInt, BigInt), denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="2a795-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2a795-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="2a795-107">signA: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a795-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="2a795-108">signB: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a795-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--bigintbigint"></a><span data-ttu-id="2a795-109">r: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="2a795-109">r : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="s--bigintbigint"></a><span data-ttu-id="2a795-110">s: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="2a795-110">s : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="t--bigintbigint"></a><span data-ttu-id="2a795-111">t: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="2a795-111">t : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="2a795-112">denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2a795-112">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="2a795-113">Kimenet: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="2a795-113">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

