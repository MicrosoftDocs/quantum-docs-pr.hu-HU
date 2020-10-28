---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716161"
---
# <a name="graycode-function"></a><span data-ttu-id="32516-102">GrayCode függvény</span><span class="sxs-lookup"><span data-stu-id="32516-102">GrayCode function</span></span>

<span data-ttu-id="32516-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="32516-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="32516-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32516-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32516-105">Szürke kódú sorozatot hoz létre</span><span class="sxs-lookup"><span data-stu-id="32516-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="32516-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="32516-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="32516-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32516-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32516-108">Bitek száma</span><span class="sxs-lookup"><span data-stu-id="32516-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="32516-109">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="32516-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="32516-110">A rekordok tömbje.</span><span class="sxs-lookup"><span data-stu-id="32516-110">Array of tuples.</span></span> <span data-ttu-id="32516-111">A rekord első értékének értéke a rekordban a GrayCode Sequence második értéke, amely a jelenlegi értékben a következőre változik.</span><span class="sxs-lookup"><span data-stu-id="32516-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>