---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fordított függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845452"
---
# <a name="reversed-function"></a><span data-ttu-id="d7784-102">Fordított függvény</span><span class="sxs-lookup"><span data-stu-id="d7784-102">Reversed function</span></span>

<span data-ttu-id="d7784-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d7784-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d7784-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7784-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7784-105">Hozzon létre egy tömböt, amely ugyanazokat az elemeket tartalmazza, mint a bemeneti tömb, de fordított sorrendben.</span><span class="sxs-lookup"><span data-stu-id="d7784-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d7784-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d7784-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="d7784-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="d7784-107">array : 'T[]</span></span>

<span data-ttu-id="d7784-108">Olyan tömb, amelynek elemeit fordított sorrendben kell másolni.</span><span class="sxs-lookup"><span data-stu-id="d7784-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="d7784-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="d7784-109">Output : 'T[]</span></span>

<span data-ttu-id="d7784-110">Az elemeket tartalmazó tömb `array[Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="d7784-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="d7784-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="d7784-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d7784-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d7784-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d7784-113">Nem</span><span class="sxs-lookup"><span data-stu-id="d7784-113">'T</span></span>

<span data-ttu-id="d7784-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="d7784-114">The type of the array elements.</span></span>