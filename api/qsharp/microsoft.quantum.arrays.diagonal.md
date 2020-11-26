---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Átlós függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221538"
---
# <a name="diagonal-function"></a><span data-ttu-id="19b75-102">Átlós függvény</span><span class="sxs-lookup"><span data-stu-id="19b75-102">Diagonal function</span></span>

<span data-ttu-id="19b75-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="19b75-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="19b75-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19b75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19b75-105">Egy kétdimenziós tömb átlós elemeinek tömbjét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="19b75-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="19b75-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="19b75-106">Description</span></span>

<span data-ttu-id="19b75-107">Ha a 2 dimenziós tömb nem rendelkezik négyzet alakú alakzattal, akkor a rendszer a sorok és oszlopok számának legkisebb feletti átlóját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="19b75-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="19b75-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="19b75-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="19b75-109">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="19b75-109">matrix : 'T[][]</span></span>

<span data-ttu-id="19b75-110">2 dimenziós mátrix a Row-Wise sorrendben</span><span class="sxs-lookup"><span data-stu-id="19b75-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="19b75-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="19b75-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="19b75-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="19b75-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="19b75-113">Nem</span><span class="sxs-lookup"><span data-stu-id="19b75-113">'T</span></span>

<span data-ttu-id="19b75-114">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="19b75-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="19b75-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="19b75-115">See Also</span></span>

- [<span data-ttu-id="19b75-116">Microsoft. Quantum. Arrays. átültetve</span><span class="sxs-lookup"><span data-stu-id="19b75-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)