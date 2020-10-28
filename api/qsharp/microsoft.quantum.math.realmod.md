---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720401"
---
# <a name="realmod-function"></a><span data-ttu-id="85c43-102">RealMod függvény</span><span class="sxs-lookup"><span data-stu-id="85c43-102">RealMod function</span></span>

<span data-ttu-id="85c43-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="85c43-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="85c43-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="85c43-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="85c43-105">Két valós szám közötti modulus kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="85c43-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="85c43-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="85c43-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="85c43-107">érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85c43-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="85c43-108">Egy valós szám $x $, amely a modulusát veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="85c43-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="85c43-109">[egyoldalas: dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85c43-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="85c43-110">Egy valós szám, amely a $x $ modulusát veszi figyelembe a tekintetében.</span><span class="sxs-lookup"><span data-stu-id="85c43-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="85c43-111">minValue: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85c43-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="85c43-112">A függvény által visszaadott legkisebb érték.</span><span class="sxs-lookup"><span data-stu-id="85c43-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="85c43-113">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85c43-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="85c43-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="85c43-114">Remarks</span></span>

<span data-ttu-id="85c43-115">Ez a függvény kiszámítja a valós modulusot úgy, hogy a valós sort becsomagolja az egység körére, majd megkeresi a bemenetnek megfelelő egység kör szögét.</span><span class="sxs-lookup"><span data-stu-id="85c43-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="85c43-116">A `minValue` bemenet ezután hatékonyan megadja az egység kör kivágásának helyét.</span><span class="sxs-lookup"><span data-stu-id="85c43-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>