---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Átlós függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719381"
---
# <a name="diagonal-function"></a><span data-ttu-id="b2b69-102">Átlós függvény</span><span class="sxs-lookup"><span data-stu-id="b2b69-102">Diagonal function</span></span>

<span data-ttu-id="b2b69-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b2b69-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b2b69-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2b69-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2b69-105">Egy kétdimenziós tömb átlós elemeinek tömbjét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b2b69-105">Returns an array of diagonal elements of a 2-dimensional array</span></span>

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b2b69-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b2b69-106">Description</span></span>

<span data-ttu-id="b2b69-107">Ha a 2 dimenziós tömb nem rendelkezik négyzet alakú alakzattal, akkor a rendszer a sorok és oszlopok számának legkisebb feletti átlóját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b2b69-107">If the 2-dimensional array has not a square shape, the diagonal over the minimum over the number of rows and columns will be returned.</span></span>

## <a name="input"></a><span data-ttu-id="b2b69-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b2b69-108">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="b2b69-109">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="b2b69-109">matrix : 'T[][]</span></span>

<span data-ttu-id="b2b69-110">2 dimenziós mátrix a Row-Wise sorrendben</span><span class="sxs-lookup"><span data-stu-id="b2b69-110">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="b2b69-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="b2b69-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b2b69-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b2b69-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2b69-113">Nem</span><span class="sxs-lookup"><span data-stu-id="b2b69-113">'T</span></span>

<span data-ttu-id="b2b69-114">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="b2b69-114">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2b69-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b2b69-115">See Also</span></span>

- [<span data-ttu-id="b2b69-116">Microsoft. Quantum. Arrays. átültetve</span><span class="sxs-lookup"><span data-stu-id="b2b69-116">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)