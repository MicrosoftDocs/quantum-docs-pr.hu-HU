---
uid: Microsoft.Quantum.Arrays.Transposed
title: Átültetett függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219991"
---
# <a name="transposed-function"></a><span data-ttu-id="152e6-102">Átültetett függvény</span><span class="sxs-lookup"><span data-stu-id="152e6-102">Transposed function</span></span>

<span data-ttu-id="152e6-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="152e6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="152e6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="152e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="152e6-105">Tömbök tömbje jelölt mátrix átültetését adja vissza.</span><span class="sxs-lookup"><span data-stu-id="152e6-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="152e6-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="152e6-106">Description</span></span>

<span data-ttu-id="152e6-107">Bemenet $r \times c $ mátrixként $r $ sorokkal és $c $ oszlopokkal.</span><span class="sxs-lookup"><span data-stu-id="152e6-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="152e6-108">A mátrix egy sor-alapú, azaz a `matrix[i][j]` (z) $i $ és a $j $ oszlopban lévő elemhez fér hozzá.</span><span class="sxs-lookup"><span data-stu-id="152e6-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="152e6-109">Ez a függvény a bemeneti mátrix átültetésének $c \times r $ mátrixot adja vissza.</span><span class="sxs-lookup"><span data-stu-id="152e6-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="152e6-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="152e6-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="152e6-111">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="152e6-111">matrix : 'T[][]</span></span>

<span data-ttu-id="152e6-112">Sor-alapú $r \times c $ mátrix</span><span class="sxs-lookup"><span data-stu-id="152e6-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="152e6-113">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="152e6-113">Output : 'T[][]</span></span>

<span data-ttu-id="152e6-114">Átültetett $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="152e6-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="152e6-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="152e6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="152e6-116">Nem</span><span class="sxs-lookup"><span data-stu-id="152e6-116">'T</span></span>

<span data-ttu-id="152e6-117">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="152e6-117">The type of each element of `matrix`.</span></span>