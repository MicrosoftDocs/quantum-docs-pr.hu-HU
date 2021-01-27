---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846256"
---
# <a name="columnat-function"></a><span data-ttu-id="d317f-102">ColumnAt függvény</span><span class="sxs-lookup"><span data-stu-id="d317f-102">ColumnAt function</span></span>

<span data-ttu-id="d317f-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d317f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d317f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d317f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d317f-105">Oszlop kibontása egy mátrixból.</span><span class="sxs-lookup"><span data-stu-id="d317f-105">Extracts a column from a matrix.</span></span>

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="d317f-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d317f-106">Description</span></span>

<span data-ttu-id="d317f-107">Ez a függvény kibontja a mátrix oszlopát a sor-Wise sorrendben.</span><span class="sxs-lookup"><span data-stu-id="d317f-107">This function extracts a column in a matrix in row-wise order.</span></span>
<span data-ttu-id="d317f-108">Sorok kibontása az első index corrsponds, ezért nincs szükség további kezelésre.</span><span class="sxs-lookup"><span data-stu-id="d317f-108">Extracting a row corrsponds to element access of the first index and therefore requires no further treatment.</span></span>

## <a name="input"></a><span data-ttu-id="d317f-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d317f-109">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="d317f-110">oszlop: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d317f-110">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d317f-111">A mátrix oszlopa</span><span class="sxs-lookup"><span data-stu-id="d317f-111">Column of the matrix</span></span>


### <a name="matrix--t"></a><span data-ttu-id="d317f-112">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="d317f-112">matrix : 'T[][]</span></span>

<span data-ttu-id="d317f-113">2 dimenziós mátrix a Row-Wise sorrendben</span><span class="sxs-lookup"><span data-stu-id="d317f-113">2-dimensional matrix in row-wise order</span></span>



## <a name="output--t"></a><span data-ttu-id="d317f-114">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="d317f-114">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d317f-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d317f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d317f-116">Nem</span><span class="sxs-lookup"><span data-stu-id="d317f-116">'T</span></span>

<span data-ttu-id="d317f-117">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="d317f-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="d317f-118">Példa</span><span class="sxs-lookup"><span data-stu-id="d317f-118">Example</span></span>

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a><span data-ttu-id="d317f-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d317f-119">See Also</span></span>

- [<span data-ttu-id="d317f-120">Microsoft. Quantum. Arrays. átültetve</span><span class="sxs-lookup"><span data-stu-id="d317f-120">Microsoft.Quantum.Arrays.Transposed</span></span>](xref:Microsoft.Quantum.Arrays.Transposed)
- [<span data-ttu-id="d317f-121">Microsoft. Quantum. Arrays. átló</span><span class="sxs-lookup"><span data-stu-id="d317f-121">Microsoft.Quantum.Arrays.Diagonal</span></span>](xref:Microsoft.Quantum.Arrays.Diagonal)