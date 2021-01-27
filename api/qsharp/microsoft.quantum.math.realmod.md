---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848349"
---
# <a name="realmod-function"></a><span data-ttu-id="472d3-102">RealMod függvény</span><span class="sxs-lookup"><span data-stu-id="472d3-102">RealMod function</span></span>

<span data-ttu-id="472d3-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="472d3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="472d3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="472d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="472d3-105">Két valós szám közötti modulus kiszámítása.</span><span class="sxs-lookup"><span data-stu-id="472d3-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="472d3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="472d3-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="472d3-107">érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="472d3-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="472d3-108">Egy valós szám $x $, amely a modulusát veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="472d3-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="472d3-109">[egyoldalas: dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="472d3-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="472d3-110">Egy valós szám, amely a $x $ modulusát veszi figyelembe a tekintetében.</span><span class="sxs-lookup"><span data-stu-id="472d3-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="472d3-111">minValue: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="472d3-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="472d3-112">A függvény által visszaadott legkisebb érték.</span><span class="sxs-lookup"><span data-stu-id="472d3-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="472d3-113">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="472d3-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="472d3-114">Példa</span><span class="sxs-lookup"><span data-stu-id="472d3-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="472d3-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="472d3-115">Remarks</span></span>

<span data-ttu-id="472d3-116">Ez a függvény kiszámítja a valós modulusot úgy, hogy a valós sort becsomagolja az egység körére, majd megkeresi a bemenetnek megfelelő egység kör szögét.</span><span class="sxs-lookup"><span data-stu-id="472d3-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="472d3-117">A `minValue` bemenet ezután hatékonyan megadja az egység kör kivágásának helyét.</span><span class="sxs-lookup"><span data-stu-id="472d3-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>