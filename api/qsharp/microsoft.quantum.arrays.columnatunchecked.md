---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842858"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="e0659-102">ColumnAtUnchecked függvény</span><span class="sxs-lookup"><span data-stu-id="e0659-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="e0659-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e0659-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e0659-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0659-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0659-105">Ez a függvény nem keres mátrix-alakzatot</span><span class="sxs-lookup"><span data-stu-id="e0659-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="e0659-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e0659-106">Description</span></span>

<span data-ttu-id="e0659-107">Ez a függvény más többdimenziós függvényekben is használható, amelyek már a bemeneti mátrixot is megtekintik egy érvényes téglalap alakú alakzathoz.</span><span class="sxs-lookup"><span data-stu-id="e0659-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="e0659-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e0659-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="e0659-109">oszlop: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e0659-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="e0659-110">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="e0659-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="e0659-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="e0659-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e0659-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e0659-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0659-113">Nem</span><span class="sxs-lookup"><span data-stu-id="e0659-113">'T</span></span>

