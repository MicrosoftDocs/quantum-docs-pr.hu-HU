---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719285"
---
# <a name="equala-function"></a><span data-ttu-id="bbabf-102">Equala függvény</span><span class="sxs-lookup"><span data-stu-id="bbabf-102">EqualA function</span></span>

<span data-ttu-id="bbabf-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bbabf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bbabf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbabf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbabf-105">Adott típusú két tömb, valamint egy, a tömbök elemeihez definiált predikátum is ellenőrzi, hogy a tömbök egyenlőek-e.</span><span class="sxs-lookup"><span data-stu-id="bbabf-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="bbabf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bbabf-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="bbabf-107">egyenlő: (nem, 'T) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bbabf-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bbabf-108">A rekordból egy függvény, amely azt vizsgálja, hogy a `('T, 'T)` `Bool` tömbök két eleme egyenlő-e.</span><span class="sxs-lookup"><span data-stu-id="bbabf-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="bbabf-109">tömb1: nem []</span><span class="sxs-lookup"><span data-stu-id="bbabf-109">array1 : 'T[]</span></span>

<span data-ttu-id="bbabf-110">Az elsőként összehasonlítható tömb.</span><span class="sxs-lookup"><span data-stu-id="bbabf-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="bbabf-111">tömb2: nem []</span><span class="sxs-lookup"><span data-stu-id="bbabf-111">array2 : 'T[]</span></span>

<span data-ttu-id="bbabf-112">Az összehasonlítandó második tömb.</span><span class="sxs-lookup"><span data-stu-id="bbabf-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bbabf-113">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bbabf-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bbabf-114">Az érték `true` , ha és csak akkor, ha `array1` és `array2` egyenlő.</span><span class="sxs-lookup"><span data-stu-id="bbabf-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="bbabf-115">Vagyis ha mindkét tömb azonos hosszúságú, és az összes elem megegyezik a által meghatározott értékkel `equal` .</span><span class="sxs-lookup"><span data-stu-id="bbabf-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bbabf-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bbabf-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbabf-117">Nem</span><span class="sxs-lookup"><span data-stu-id="bbabf-117">'T</span></span>

<span data-ttu-id="bbabf-118">Az egyes tömbök elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="bbabf-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="bbabf-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bbabf-119">Remarks</span></span>

<span data-ttu-id="bbabf-120">Ez a függvény általános típusokhoz van definiálva; azaz, ha két tömb `'T[]` és egy függvény van `equal: ('T, 'T) -> Bool` , akkor ez a függvény egy értéket ad vissza, `Bool` amely jelzi, hogy a tömbök egyenlőek-e.</span><span class="sxs-lookup"><span data-stu-id="bbabf-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="bbabf-121">Ha két tömbnek egyenlőnek kell lennie, akkor egyenlőnek kell lennie, és a tömbök azonos helyein lévő elemeknek egyenlőnek kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="bbabf-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>