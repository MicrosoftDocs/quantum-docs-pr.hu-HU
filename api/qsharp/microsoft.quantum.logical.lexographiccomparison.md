---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709903"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="d6107-102">LexographicComparison függvény</span><span class="sxs-lookup"><span data-stu-id="d6107-102">LexographicComparison function</span></span>

<span data-ttu-id="d6107-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d6107-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d6107-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6107-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6107-105">Az összehasonlítási függvény egy új függvényt ad vissza, amely a lexographically összehasonlítja a két tömböt.</span><span class="sxs-lookup"><span data-stu-id="d6107-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="d6107-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d6107-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="d6107-107">elementComparison: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d6107-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d6107-108">Egy függvény, amely összehasonlítja a két elemet `x` , `y` és visszaadja, ha a `x` értéke kisebb vagy egyenlő `y` .</span><span class="sxs-lookup"><span data-stu-id="d6107-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="d6107-109">Kimenet: ('T [], 'T [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d6107-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d6107-110">Függvény, amely összehasonlítja a két tömböt, `xs` `ys` és visszaadja, ha a `xs` `ys` lexographical sorrendje előtt vagy azzal egyenlően történik.</span><span class="sxs-lookup"><span data-stu-id="d6107-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d6107-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d6107-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d6107-112">Nem</span><span class="sxs-lookup"><span data-stu-id="d6107-112">'T</span></span>

<span data-ttu-id="d6107-113">Az összehasonlítható tömbök elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="d6107-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6107-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d6107-114">Remarks</span></span>

<span data-ttu-id="d6107-115">A két tömb közötti lexographic `xs` -összehasonlítást `ys` a következő eljárás határozza meg.</span><span class="sxs-lookup"><span data-stu-id="d6107-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="d6107-116">Tegyük fel, hogy két elem `x` és `y` egyenértékű, ha `elementComparison(x, y)` `elementComparison(y, x)` mindkettő igaz.</span><span class="sxs-lookup"><span data-stu-id="d6107-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="d6107-117">Mindkét tömb össze van hasonlítva az Element-by-Element értékkel, amíg az elemek első párja nem egyenértékű.</span><span class="sxs-lookup"><span data-stu-id="d6107-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="d6107-118">Az elsőnek megfelelően megjelenő elemet tartalmazó tömb a `elementComparison` lexographical megrendelésének első lépéseként következik be.</span><span class="sxs-lookup"><span data-stu-id="d6107-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="d6107-119">Ha a rendszer nem talál nem megfelelő elemeket, és egy tömb hosszabb a többinél, akkor a rövidebb tömb jelenik meg először.</span><span class="sxs-lookup"><span data-stu-id="d6107-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6107-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d6107-120">See Also</span></span>

- [<span data-ttu-id="d6107-121">Microsoft. Quantum. Arrays. rendezve</span><span class="sxs-lookup"><span data-stu-id="d6107-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)