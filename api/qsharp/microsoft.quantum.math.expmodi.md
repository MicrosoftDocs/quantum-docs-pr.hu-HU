---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228490"
---
# <a name="expmodi-function"></a><span data-ttu-id="a620d-102">ExpModI függvény</span><span class="sxs-lookup"><span data-stu-id="a620d-102">ExpModI function</span></span>

<span data-ttu-id="a620d-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a620d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a620d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a620d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a620d-105">Egy adott hatványra kiváltott egész számot ad vissza egy adott modulusra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="a620d-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="a620d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="a620d-106">Description</span></span>

<span data-ttu-id="a620d-107">A expBase $x $, a Power by $p $ és a modulus $N $ értéket jelöli.</span><span class="sxs-lookup"><span data-stu-id="a620d-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="a620d-108">A függvény a $x ^ p \operatorname{mod} N $ értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="a620d-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="a620d-109">Feltételezzük, hogy $N $, $x $ értéke pozitív, és a teljesítmény nem negatív.</span><span class="sxs-lookup"><span data-stu-id="a620d-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="a620d-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a620d-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="a620d-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a620d-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="a620d-112">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a620d-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="a620d-113">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a620d-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="a620d-114">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a620d-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="a620d-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a620d-115">Remarks</span></span>

<span data-ttu-id="a620d-116">Időt vesz igénybe a bitek számával `power` , nem pedig `power` magával.</span><span class="sxs-lookup"><span data-stu-id="a620d-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>