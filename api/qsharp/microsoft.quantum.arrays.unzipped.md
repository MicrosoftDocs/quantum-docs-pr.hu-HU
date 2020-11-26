---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Kibontott függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219957"
---
# <a name="unzipped-function"></a><span data-ttu-id="4a294-102">Kibontott függvény</span><span class="sxs-lookup"><span data-stu-id="4a294-102">Unzipped function</span></span>

<span data-ttu-id="4a294-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4a294-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4a294-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a294-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a294-105">A 2-rekordok tömbje egy két tömbből álló tömböt ad vissza, amely a bemeneti tömb rekordok elemeit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4a294-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="4a294-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4a294-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="4a294-107">ARR: (nem, ' U) []</span><span class="sxs-lookup"><span data-stu-id="4a294-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="4a294-108">2 – rekordok tartalmazó tömb</span><span class="sxs-lookup"><span data-stu-id="4a294-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="4a294-109">Kimenet: ('T [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="4a294-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="4a294-110">Két tömb, amely a bemeneti rekordok első elemeit tartalmazza, a második pedig a bemeneti rekordok összes elemét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4a294-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4a294-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4a294-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a294-112">Nem</span><span class="sxs-lookup"><span data-stu-id="4a294-112">'T</span></span>

<span data-ttu-id="4a294-113">Az egyes rekordokban az első elem típusa</span><span class="sxs-lookup"><span data-stu-id="4a294-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="4a294-114">' U</span><span class="sxs-lookup"><span data-stu-id="4a294-114">'U</span></span>

<span data-ttu-id="4a294-115">Az egyes rekordokban szereplő második elem típusa</span><span class="sxs-lookup"><span data-stu-id="4a294-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="4a294-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4a294-116">See Also</span></span>

- [<span data-ttu-id="4a294-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="4a294-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)