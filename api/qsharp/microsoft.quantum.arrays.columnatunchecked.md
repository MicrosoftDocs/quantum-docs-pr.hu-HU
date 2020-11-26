---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 06fce23bbf7142ee0e0b0ed3f2c0578676f2097b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221589"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="9ebd7-102">ColumnAtUnchecked függvény</span><span class="sxs-lookup"><span data-stu-id="9ebd7-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="9ebd7-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9ebd7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9ebd7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ebd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ebd7-105">Ez a függvény nem keres mátrix-alakzatot</span><span class="sxs-lookup"><span data-stu-id="9ebd7-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="9ebd7-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="9ebd7-106">Description</span></span>

<span data-ttu-id="9ebd7-107">Ez a függvény más többdimenziós függvényekben is használható, amelyek már a bemeneti mátrixot is megtekintik egy érvényes téglalap alakú alakzathoz.</span><span class="sxs-lookup"><span data-stu-id="9ebd7-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="9ebd7-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9ebd7-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="9ebd7-109">oszlop: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9ebd7-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="9ebd7-110">mátrix: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="9ebd7-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="9ebd7-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="9ebd7-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ebd7-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9ebd7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ebd7-113">Nem</span><span class="sxs-lookup"><span data-stu-id="9ebd7-113">'T</span></span>

