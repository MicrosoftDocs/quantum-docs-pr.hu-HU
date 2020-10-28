---
uid: Microsoft.Quantum.Arrays.Transposed
title: Átültetett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718816"
---
# <a name="transposed-function"></a><span data-ttu-id="4e870-102">Átültetett függvény</span><span class="sxs-lookup"><span data-stu-id="4e870-102">Transposed function</span></span>

<span data-ttu-id="4e870-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4e870-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4e870-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e870-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e870-105">Tömbök tömbje jelölt mátrix átültetését adja vissza.</span><span class="sxs-lookup"><span data-stu-id="4e870-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="4e870-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4e870-106">Description</span></span>

<span data-ttu-id="4e870-107">Bemenet $r \times c $ mátrixként $r $ sorokkal és $c $ oszlopokkal.</span><span class="sxs-lookup"><span data-stu-id="4e870-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="4e870-108">A mátrix egy sor-alapú, azaz a `matrix[i][j]` (z) $i $ és a $j $ oszlopban lévő elemhez fér hozzá.</span><span class="sxs-lookup"><span data-stu-id="4e870-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="4e870-109">Ez a függvény a bemeneti mátrix átültetésének $c \times r $ mátrixot adja vissza.</span><span class="sxs-lookup"><span data-stu-id="4e870-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="4e870-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4e870-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="4e870-111">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="4e870-111">matrix : 'T[][]</span></span>

<span data-ttu-id="4e870-112">Sor-alapú $r \times c $ mátrix</span><span class="sxs-lookup"><span data-stu-id="4e870-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="4e870-113">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="4e870-113">Output : 'T[][]</span></span>

<span data-ttu-id="4e870-114">Átültetett $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="4e870-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4e870-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4e870-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e870-116">Nem</span><span class="sxs-lookup"><span data-stu-id="4e870-116">'T</span></span>

<span data-ttu-id="4e870-117">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="4e870-117">The type of each element of `matrix`.</span></span>