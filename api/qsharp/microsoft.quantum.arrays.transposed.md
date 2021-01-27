---
uid: Microsoft.Quantum.Arrays.Transposed
title: Átültetett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850932"
---
# <a name="transposed-function"></a><span data-ttu-id="41564-102">Átültetett függvény</span><span class="sxs-lookup"><span data-stu-id="41564-102">Transposed function</span></span>

<span data-ttu-id="41564-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="41564-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="41564-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41564-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41564-105">Tömbök tömbje jelölt mátrix átültetését adja vissza.</span><span class="sxs-lookup"><span data-stu-id="41564-105">Returns the transpose of a matrix represented as an array of arrays.</span></span>

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="41564-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="41564-106">Description</span></span>

<span data-ttu-id="41564-107">Bemenet $r \times c $ mátrixként $r $ sorokkal és $c $ oszlopokkal.</span><span class="sxs-lookup"><span data-stu-id="41564-107">Input as an $r \times c$ matrix with $r$ rows and $c$ columns.</span></span>  <span data-ttu-id="41564-108">A mátrix egy sor-alapú, azaz a `matrix[i][j]` (z) $i $ és a $j $ oszlopban lévő elemhez fér hozzá.</span><span class="sxs-lookup"><span data-stu-id="41564-108">The matrix is row-based, i.e., `matrix[i][j]` accesses the element at row $i$ and column $j$.</span></span>

<span data-ttu-id="41564-109">Ez a függvény a bemeneti mátrix átültetésének $c \times r $ mátrixot adja vissza.</span><span class="sxs-lookup"><span data-stu-id="41564-109">This function returns the $c \times r$ matrix that is the transpose of the input matrix.</span></span>

## <a name="input"></a><span data-ttu-id="41564-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="41564-110">Input</span></span>

### <a name="matrix--t"></a><span data-ttu-id="41564-111">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="41564-111">matrix : 'T[][]</span></span>

<span data-ttu-id="41564-112">Sor-alapú $r \times c $ mátrix</span><span class="sxs-lookup"><span data-stu-id="41564-112">Row-based $r \times c$ matrix</span></span>



## <a name="output--t"></a><span data-ttu-id="41564-113">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="41564-113">Output : 'T[][]</span></span>

<span data-ttu-id="41564-114">Átültetett $c \times r $ Matrix</span><span class="sxs-lookup"><span data-stu-id="41564-114">Transposed $c \times r$ matrix</span></span>

## <a name="type-parameters"></a><span data-ttu-id="41564-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="41564-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41564-116">Nem</span><span class="sxs-lookup"><span data-stu-id="41564-116">'T</span></span>

<span data-ttu-id="41564-117">Az egyes elemeinek típusa `matrix` .</span><span class="sxs-lookup"><span data-stu-id="41564-117">The type of each element of `matrix`.</span></span>

## <a name="example"></a><span data-ttu-id="41564-118">Példa</span><span class="sxs-lookup"><span data-stu-id="41564-118">Example</span></span>

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```