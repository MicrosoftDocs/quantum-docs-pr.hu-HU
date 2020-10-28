---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719452"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="fc1c0-102">ColumnAtUnchecked függvény</span><span class="sxs-lookup"><span data-stu-id="fc1c0-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="fc1c0-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fc1c0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fc1c0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc1c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc1c0-105">Ez a függvény nem keres mátrix-alakzatot</span><span class="sxs-lookup"><span data-stu-id="fc1c0-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="fc1c0-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="fc1c0-106">Description</span></span>

<span data-ttu-id="fc1c0-107">Ez a függvény más többdimenziós függvényekben is használható, amelyek már a bemeneti mátrixot is megtekintik egy érvényes téglalap alakú alakzathoz.</span><span class="sxs-lookup"><span data-stu-id="fc1c0-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="fc1c0-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fc1c0-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="fc1c0-109">oszlop: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc1c0-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="fc1c0-110">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="fc1c0-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="fc1c0-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="fc1c0-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fc1c0-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="fc1c0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc1c0-113">Nem</span><span class="sxs-lookup"><span data-stu-id="fc1c0-113">'T</span></span>

