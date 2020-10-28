---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723361"
---
# <a name="expmodi-function"></a><span data-ttu-id="7f6ae-102">ExpModI függvény</span><span class="sxs-lookup"><span data-stu-id="7f6ae-102">ExpModI function</span></span>

<span data-ttu-id="7f6ae-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7f6ae-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7f6ae-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f6ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f6ae-105">Egy adott hatványra kiváltott egész számot ad vissza egy adott modulusra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="7f6ae-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="7f6ae-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="7f6ae-106">Description</span></span>

<span data-ttu-id="7f6ae-107">A expBase $x $, a Power by $p $ és a modulus $N $ értéket jelöli.</span><span class="sxs-lookup"><span data-stu-id="7f6ae-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="7f6ae-108">A függvény a $x ^ p \operatorname{mod} N $ értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="7f6ae-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="7f6ae-109">Feltételezzük, hogy $N $, $x $ értéke pozitív, és a teljesítmény nem negatív.</span><span class="sxs-lookup"><span data-stu-id="7f6ae-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="7f6ae-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7f6ae-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="7f6ae-111">expBase: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f6ae-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="7f6ae-112">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f6ae-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="7f6ae-113">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f6ae-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="7f6ae-114">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f6ae-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="7f6ae-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7f6ae-115">Remarks</span></span>

<span data-ttu-id="7f6ae-116">Időt vesz igénybe a bitek számával `power` , nem pedig `power` magával.</span><span class="sxs-lookup"><span data-stu-id="7f6ae-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>