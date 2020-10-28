---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719453"
---
# <a name="columnat-function"></a><span data-ttu-id="c1fc3-102">ColumnAt függvény</span><span class="sxs-lookup"><span data-stu-id="c1fc3-102">ColumnAt function</span></span>

<span data-ttu-id="c1fc3-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c1fc3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c1fc3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1fc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1fc3-105">Oszlop kibontása egy mátrixból.</span><span class="sxs-lookup"><span data-stu-id="c1fc3-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="c1fc3-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="c1fc3-106">Description</span></span>

<span data-ttu-id="c1fc3-107">Ez a függvény kibontja a mátrix oszlopát a sor-Wise sorrendben.</span><span class="sxs-lookup"><span data-stu-id="c1fc3-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="c1fc3-108">Sorok kibontása az első index corrsponds, ezért nincs szükség további kezelésre.</span><span class="sxs-lookup"><span data-stu-id="c1fc3-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="c1fc3-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c1fc3-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="c1fc3-110">oszlop: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1fc3-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1fc3-111">A mátrix oszlopa</span><span class="sxs-lookup"><span data-stu-id="c1fc3-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="c1fc3-112">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="c1fc3-112">matrix : 'T[][]</span></span>

<span data-ttu-id="c1fc3-113">2 dimenziós mátrix a Row-Wise sorrendben</span><span class="sxs-lookup"><span data-stu-id="c1fc3-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="c1fc3-114">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="c1fc3-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c1fc3-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c1fc3-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c1fc3-116">Nem</span><span class="sxs-lookup"><span data-stu-id="c1fc3-116">'T</span></span>

<span data-ttu-id="c1fc3-117">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="c1fc3-117">The type of each element of `matrix`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1fc3-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c1fc3-118">See Also</span></span>

- [<span data-ttu-id="c1fc3-119">Microsoft. Quantum. Arrays. átültetve</span><span class="sxs-lookup"><span data-stu-id="c1fc3-119">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="c1fc3-120">Microsoft. Quantum. Arrays. átló</span><span class="sxs-lookup"><span data-stu-id="c1fc3-120">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)