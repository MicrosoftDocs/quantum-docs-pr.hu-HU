---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210746"
---
# <a name="expmodl-function"></a><span data-ttu-id="fe889-102">ExpModL függvény</span><span class="sxs-lookup"><span data-stu-id="fe889-102">ExpModL function</span></span>

<span data-ttu-id="fe889-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fe889-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fe889-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe889-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe889-105">Egy adott hatványra kiváltott egész számot ad vissza egy adott modulusra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="fe889-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="fe889-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="fe889-106">Description</span></span>

<span data-ttu-id="fe889-107">A expBase $x $, a Power by $p $ és a modulus $N $ értéket jelöli.</span><span class="sxs-lookup"><span data-stu-id="fe889-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="fe889-108">A függvény a $x ^ p \operatorname{mod} N $ értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fe889-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="fe889-109">Feltételezzük, hogy $N $, $x $ értéke pozitív, és a teljesítmény nem negatív.</span><span class="sxs-lookup"><span data-stu-id="fe889-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="fe889-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fe889-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="fe889-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe889-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="fe889-112">Power: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe889-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="fe889-113">modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe889-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="fe889-114">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe889-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe889-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fe889-115">Remarks</span></span>

<span data-ttu-id="fe889-116">Időt vesz igénybe a bitek számával `power` , nem pedig `power` magával.</span><span class="sxs-lookup"><span data-stu-id="fe889-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>