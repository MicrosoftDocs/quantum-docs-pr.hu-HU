---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fordított függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220433"
---
# <a name="reversed-function"></a><span data-ttu-id="dd489-102">Fordított függvény</span><span class="sxs-lookup"><span data-stu-id="dd489-102">Reversed function</span></span>

<span data-ttu-id="dd489-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dd489-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dd489-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd489-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd489-105">Hozzon létre egy tömböt, amely ugyanazokat az elemeket tartalmazza, mint a bemeneti tömb, de fordított sorrendben.</span><span class="sxs-lookup"><span data-stu-id="dd489-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="dd489-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dd489-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="dd489-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="dd489-107">array : 'T[]</span></span>

<span data-ttu-id="dd489-108">Olyan tömb, amelynek elemeit fordított sorrendben kell másolni.</span><span class="sxs-lookup"><span data-stu-id="dd489-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="dd489-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="dd489-109">Output : 'T[]</span></span>

<span data-ttu-id="dd489-110">Az elemeket tartalmazó tömb `array[Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="dd489-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="dd489-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="dd489-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dd489-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dd489-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dd489-113">Nem</span><span class="sxs-lookup"><span data-stu-id="dd489-113">'T</span></span>

<span data-ttu-id="dd489-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="dd489-114">The type of the array elements.</span></span>