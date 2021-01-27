---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848525"
---
# <a name="indexof-function"></a><span data-ttu-id="8cda1-102">IndexOf függvény</span><span class="sxs-lookup"><span data-stu-id="8cda1-102">IndexOf function</span></span>

<span data-ttu-id="8cda1-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8cda1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8cda1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8cda1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8cda1-105">Egy olyan tömb első elemének első indexét adja vissza, amely megfelel egy adott predikátumnak.</span><span class="sxs-lookup"><span data-stu-id="8cda1-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="8cda1-106">Ha nem létezik ilyen elem, a a-1 értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="8cda1-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="8cda1-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8cda1-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="8cda1-108">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8cda1-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8cda1-109">Egy predikátum-függvény, amely a tömb elemein működik.</span><span class="sxs-lookup"><span data-stu-id="8cda1-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="8cda1-110">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="8cda1-110">arr : 'T[]</span></span>

<span data-ttu-id="8cda1-111">A megadott predikátum használatával keresendő tömb.</span><span class="sxs-lookup"><span data-stu-id="8cda1-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="8cda1-112">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8cda1-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8cda1-113">Vagy a legkisebb index `idx` , amely `predicate(arr[idx])` igaz, vagy-1, ha nincs ilyen elem.</span><span class="sxs-lookup"><span data-stu-id="8cda1-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8cda1-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8cda1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8cda1-115">Nem</span><span class="sxs-lookup"><span data-stu-id="8cda1-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="8cda1-116">Példa</span><span class="sxs-lookup"><span data-stu-id="8cda1-116">Example</span></span>

<span data-ttu-id="8cda1-117">Tegyük fel, hogy `IsEven : Int -> Bool` egy olyan függvény, amely `true` csak akkor adja vissza, ha a bemenete páros.</span><span class="sxs-lookup"><span data-stu-id="8cda1-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="8cda1-118">Ezt követően a használatával `IndexOf` megkeresheti a tömb első páros elemét is:</span><span class="sxs-lookup"><span data-stu-id="8cda1-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```