---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Kibontott függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845367"
---
# <a name="unzipped-function"></a><span data-ttu-id="67277-102">Kibontott függvény</span><span class="sxs-lookup"><span data-stu-id="67277-102">Unzipped function</span></span>

<span data-ttu-id="67277-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="67277-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="67277-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67277-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67277-105">A 2-rekordok tömbje egy két tömbből álló tömböt ad vissza, amely a bemeneti tömb rekordok elemeit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="67277-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="67277-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="67277-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="67277-107">ARR: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="67277-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="67277-108">2 – rekordok tartalmazó tömb</span><span class="sxs-lookup"><span data-stu-id="67277-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="67277-109">Kimenet: ('T [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="67277-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="67277-110">Két tömb, amely a bemeneti rekordok első elemeit tartalmazza, a második pedig a bemeneti rekordok összes elemét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="67277-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="67277-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="67277-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67277-112">Nem</span><span class="sxs-lookup"><span data-stu-id="67277-112">'T</span></span>

<span data-ttu-id="67277-113">Az egyes rekordokban az első elem típusa</span><span class="sxs-lookup"><span data-stu-id="67277-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="67277-114">' U</span><span class="sxs-lookup"><span data-stu-id="67277-114">'U</span></span>

<span data-ttu-id="67277-115">Az egyes rekordokban szereplő második elem típusa</span><span class="sxs-lookup"><span data-stu-id="67277-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="67277-116">Példa</span><span class="sxs-lookup"><span data-stu-id="67277-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="67277-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="67277-117">See Also</span></span>

- [<span data-ttu-id="67277-118">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="67277-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)