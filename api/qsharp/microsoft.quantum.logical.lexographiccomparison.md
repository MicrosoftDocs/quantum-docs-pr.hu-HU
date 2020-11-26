---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197584"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="b3bd3-102">LexographicComparison függvény</span><span class="sxs-lookup"><span data-stu-id="b3bd3-102">LexographicComparison function</span></span>

<span data-ttu-id="b3bd3-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b3bd3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b3bd3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b3bd3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b3bd3-105">Az összehasonlítási függvény egy új függvényt ad vissza, amely a lexographically összehasonlítja a két tömböt.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="b3bd3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b3bd3-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="b3bd3-107">elementComparison: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b3bd3-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b3bd3-108">Egy függvény, amely összehasonlítja a két elemet `x` , `y` és visszaadja, ha a `x` értéke kisebb vagy egyenlő `y` .</span><span class="sxs-lookup"><span data-stu-id="b3bd3-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="b3bd3-109">Kimenet: ('T [], 'T [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b3bd3-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b3bd3-110">Függvény, amely összehasonlítja a két tömböt, `xs` `ys` és visszaadja, ha a `xs` `ys` lexographical sorrendje előtt vagy azzal egyenlően történik.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b3bd3-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b3bd3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b3bd3-112">Nem</span><span class="sxs-lookup"><span data-stu-id="b3bd3-112">'T</span></span>

<span data-ttu-id="b3bd3-113">Az összehasonlítható tömbök elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3bd3-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b3bd3-114">Remarks</span></span>

<span data-ttu-id="b3bd3-115">A két tömb közötti lexographic `xs` -összehasonlítást `ys` a következő eljárás határozza meg.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="b3bd3-116">Tegyük fel, hogy két elem `x` és `y` egyenértékű, ha `elementComparison(x, y)` `elementComparison(y, x)` mindkettő igaz.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="b3bd3-117">Mindkét tömb össze van hasonlítva az Element-by-Element értékkel, amíg az elemek első párja nem egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="b3bd3-118">Az elsőnek megfelelően megjelenő elemet tartalmazó tömb a `elementComparison` lexographical megrendelésének első lépéseként következik be.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="b3bd3-119">Ha a rendszer nem talál nem megfelelő elemeket, és egy tömb hosszabb a többinél, akkor a rövidebb tömb jelenik meg először.</span><span class="sxs-lookup"><span data-stu-id="b3bd3-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3bd3-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b3bd3-120">See Also</span></span>

- [<span data-ttu-id="b3bd3-121">Microsoft. Quantum. Arrays. rendezve</span><span class="sxs-lookup"><span data-stu-id="b3bd3-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)