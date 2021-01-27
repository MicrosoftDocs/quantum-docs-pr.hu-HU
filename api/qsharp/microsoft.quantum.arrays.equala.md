---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848689"
---
# <a name="equala-function"></a><span data-ttu-id="c328a-102">Equala függvény</span><span class="sxs-lookup"><span data-stu-id="c328a-102">EqualA function</span></span>

<span data-ttu-id="c328a-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c328a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c328a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c328a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c328a-105">Adott típusú két tömb, valamint egy, a tömbök elemeihez definiált predikátum is ellenőrzi, hogy a tömbök egyenlőek-e.</span><span class="sxs-lookup"><span data-stu-id="c328a-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="c328a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c328a-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="c328a-107">egyenlő: (nem, 'T) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c328a-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c328a-108">A rekordból egy függvény, amely azt vizsgálja, hogy a `('T, 'T)` `Bool` tömbök két eleme egyenlő-e.</span><span class="sxs-lookup"><span data-stu-id="c328a-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="c328a-109">tömb1: nem []</span><span class="sxs-lookup"><span data-stu-id="c328a-109">array1 : 'T[]</span></span>

<span data-ttu-id="c328a-110">Az elsőként összehasonlítható tömb.</span><span class="sxs-lookup"><span data-stu-id="c328a-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="c328a-111">tömb2: nem []</span><span class="sxs-lookup"><span data-stu-id="c328a-111">array2 : 'T[]</span></span>

<span data-ttu-id="c328a-112">Az összehasonlítandó második tömb.</span><span class="sxs-lookup"><span data-stu-id="c328a-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c328a-113">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c328a-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c328a-114">Az érték `true` , ha és csak akkor, ha `array1` és `array2` egyenlő.</span><span class="sxs-lookup"><span data-stu-id="c328a-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="c328a-115">Vagyis ha mindkét tömb azonos hosszúságú, és az összes elem megegyezik a által meghatározott értékkel `equal` .</span><span class="sxs-lookup"><span data-stu-id="c328a-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c328a-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c328a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c328a-117">Nem</span><span class="sxs-lookup"><span data-stu-id="c328a-117">'T</span></span>

<span data-ttu-id="c328a-118">Az egyes tömbök elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="c328a-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="c328a-119">Példa</span><span class="sxs-lookup"><span data-stu-id="c328a-119">Example</span></span>

<span data-ttu-id="c328a-120">A következő kód ellenőrzi, hogy a tömbök különböző párjai egyenlőek-e:</span><span class="sxs-lookup"><span data-stu-id="c328a-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="c328a-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c328a-121">Remarks</span></span>

<span data-ttu-id="c328a-122">Ez a függvény általános típusokhoz van definiálva; azaz, ha két tömb `'T[]` és egy függvény van `equal: ('T, 'T) -> Bool` , akkor ez a függvény egy értéket ad vissza, `Bool` amely jelzi, hogy a tömbök egyenlőek-e.</span><span class="sxs-lookup"><span data-stu-id="c328a-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="c328a-123">Ha két tömbnek egyenlőnek kell lennie, akkor egyenlőnek kell lennie, és a tömbök azonos helyein lévő elemeknek egyenlőnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="c328a-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>