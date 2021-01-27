---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Átlós függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842828"
---
# <a name="diagonal-function"></a><span data-ttu-id="78d93-102">Átlós függvény</span><span class="sxs-lookup"><span data-stu-id="78d93-102">Diagonal function</span></span>

<span data-ttu-id="78d93-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="78d93-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="78d93-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78d93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78d93-105">Egy kétdimenziós tömb átlós elemeinek tömbjét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="78d93-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="78d93-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="78d93-106">Description</span></span>

<span data-ttu-id="78d93-107">Ha a 2 dimenziós tömb nem rendelkezik négyzet alakú alakzattal, akkor a rendszer a sorok és oszlopok számának legkisebb feletti átlóját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="78d93-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="78d93-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="78d93-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="78d93-109">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="78d93-109">matrix : 'T[][]</span></span>

<span data-ttu-id="78d93-110">2 dimenziós mátrix a Row-Wise sorrendben</span><span class="sxs-lookup"><span data-stu-id="78d93-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="78d93-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="78d93-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="78d93-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="78d93-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78d93-113">Nem</span><span class="sxs-lookup"><span data-stu-id="78d93-113">'T</span></span>

<span data-ttu-id="78d93-114">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="78d93-114">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="78d93-115">Példa</span><span class="sxs-lookup"><span data-stu-id="78d93-115">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a><span data-ttu-id="78d93-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="78d93-116">See Also</span></span>

- [<span data-ttu-id="78d93-117">Microsoft. Quantum. Arrays. átültetve</span><span class="sxs-lookup"><span data-stu-id="78d93-117">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)