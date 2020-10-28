---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Kibontott függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718792"
---
# <a name="unzipped-function"></a><span data-ttu-id="d32f5-102">Kibontott függvény</span><span class="sxs-lookup"><span data-stu-id="d32f5-102">Unzipped function</span></span>

<span data-ttu-id="d32f5-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d32f5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d32f5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d32f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d32f5-105">A 2-rekordok tömbje egy két tömbből álló tömböt ad vissza, amely a bemeneti tömb rekordok elemeit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d32f5-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="d32f5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d32f5-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="d32f5-107">ARR: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="d32f5-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="d32f5-108">2 – rekordok tartalmazó tömb</span><span class="sxs-lookup"><span data-stu-id="d32f5-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="d32f5-109">Kimenet: ('T [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="d32f5-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="d32f5-110">Két tömb, amely a bemeneti rekordok első elemeit tartalmazza, a második pedig a bemeneti rekordok összes elemét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d32f5-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d32f5-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d32f5-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d32f5-112">Nem</span><span class="sxs-lookup"><span data-stu-id="d32f5-112">'T</span></span>

<span data-ttu-id="d32f5-113">Az egyes rekordokban az első elem típusa</span><span class="sxs-lookup"><span data-stu-id="d32f5-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="d32f5-114">' U</span><span class="sxs-lookup"><span data-stu-id="d32f5-114">'U</span></span>

<span data-ttu-id="d32f5-115">Az egyes rekordokban szereplő második elem típusa</span><span class="sxs-lookup"><span data-stu-id="d32f5-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="d32f5-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d32f5-116">See Also</span></span>

- [<span data-ttu-id="d32f5-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="d32f5-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)