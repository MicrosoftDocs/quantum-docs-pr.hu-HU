---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228253"
---
# <a name="realmod-function"></a><span data-ttu-id="5e5d4-102">RealMod függvény</span><span class="sxs-lookup"><span data-stu-id="5e5d4-102">RealMod function</span></span>

<span data-ttu-id="5e5d4-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5e5d4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5e5d4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e5d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e5d4-105">Két valós szám közötti modulus kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="5e5d4-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="5e5d4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5e5d4-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="5e5d4-107">érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e5d4-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e5d4-108">Egy valós szám $x $, amely a modulusát veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="5e5d4-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="5e5d4-109">[egyoldalas: dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e5d4-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e5d4-110">Egy valós szám, amely a $x $ modulusát veszi figyelembe a tekintetében.</span><span class="sxs-lookup"><span data-stu-id="5e5d4-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="5e5d4-111">minValue: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e5d4-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e5d4-112">A függvény által visszaadott legkisebb érték.</span><span class="sxs-lookup"><span data-stu-id="5e5d4-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="5e5d4-113">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e5d4-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="5e5d4-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5e5d4-114">Remarks</span></span>

<span data-ttu-id="5e5d4-115">Ez a függvény kiszámítja a valós modulusot úgy, hogy a valós sort becsomagolja az egység körére, majd megkeresi a bemenetnek megfelelő egység kör szögét.</span><span class="sxs-lookup"><span data-stu-id="5e5d4-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="5e5d4-116">A `minValue` bemenet ezután hatékonyan megadja az egység kör kivágásának helyét.</span><span class="sxs-lookup"><span data-stu-id="5e5d4-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>