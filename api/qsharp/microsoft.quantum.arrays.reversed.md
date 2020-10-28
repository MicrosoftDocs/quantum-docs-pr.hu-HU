---
uid: Microsoft.Quantum.Arrays.Reversed
title: Fordított függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718912"
---
# <a name="reversed-function"></a><span data-ttu-id="58f11-102">Fordított függvény</span><span class="sxs-lookup"><span data-stu-id="58f11-102">Reversed function</span></span>

<span data-ttu-id="58f11-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="58f11-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="58f11-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58f11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58f11-105">Hozzon létre egy tömböt, amely ugyanazokat az elemeket tartalmazza, mint a bemeneti tömb, de fordított sorrendben.</span><span class="sxs-lookup"><span data-stu-id="58f11-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="58f11-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="58f11-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="58f11-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="58f11-107">array : 'T[]</span></span>

<span data-ttu-id="58f11-108">Olyan tömb, amelynek elemeit fordított sorrendben kell másolni.</span><span class="sxs-lookup"><span data-stu-id="58f11-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="58f11-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="58f11-109">Output : 'T[]</span></span>

<span data-ttu-id="58f11-110">Az elemeket tartalmazó tömb `array[Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="58f11-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="58f11-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="58f11-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="58f11-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="58f11-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58f11-113">Nem</span><span class="sxs-lookup"><span data-stu-id="58f11-113">'T</span></span>

<span data-ttu-id="58f11-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="58f11-114">The type of the array elements.</span></span>