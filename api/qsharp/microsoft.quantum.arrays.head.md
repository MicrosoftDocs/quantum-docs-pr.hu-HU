---
uid: Microsoft.Quantum.Arrays.Head
title: Head függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719188"
---
# <a name="head-function"></a><span data-ttu-id="5ba38-102">Head függvény</span><span class="sxs-lookup"><span data-stu-id="5ba38-102">Head function</span></span>

<span data-ttu-id="5ba38-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5ba38-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5ba38-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ba38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ba38-105">A tömb első elemét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="5ba38-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="5ba38-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5ba38-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="5ba38-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="5ba38-107">array : 'A[]</span></span>

<span data-ttu-id="5ba38-108">Az első elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="5ba38-108">Array of which the first element is taken.</span></span> <span data-ttu-id="5ba38-109">A tömbnek legalább 1 karakterből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="5ba38-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="5ba38-110">Kimenet: "A"</span><span class="sxs-lookup"><span data-stu-id="5ba38-110">Output : 'A</span></span>

<span data-ttu-id="5ba38-111">A tömb első eleme.</span><span class="sxs-lookup"><span data-stu-id="5ba38-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5ba38-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="5ba38-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="5ba38-113">"A</span><span class="sxs-lookup"><span data-stu-id="5ba38-113">'A</span></span>

<span data-ttu-id="5ba38-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="5ba38-114">The type of the array elements.</span></span>