---
uid: Microsoft.Quantum.Arrays.Head
title: Head függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221113"
---
# <a name="head-function"></a><span data-ttu-id="fb501-102">Head függvény</span><span class="sxs-lookup"><span data-stu-id="fb501-102">Head function</span></span>

<span data-ttu-id="fb501-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fb501-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fb501-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb501-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb501-105">A tömb első elemét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="fb501-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="fb501-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fb501-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="fb501-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="fb501-107">array : 'A[]</span></span>

<span data-ttu-id="fb501-108">Az első elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="fb501-108">Array of which the first element is taken.</span></span> <span data-ttu-id="fb501-109">A tömbnek legalább 1 karakterből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="fb501-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="fb501-110">Kimenet: "A"</span><span class="sxs-lookup"><span data-stu-id="fb501-110">Output : 'A</span></span>

<span data-ttu-id="fb501-111">A tömb első eleme.</span><span class="sxs-lookup"><span data-stu-id="fb501-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fb501-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="fb501-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="fb501-113">"A</span><span class="sxs-lookup"><span data-stu-id="fb501-113">'A</span></span>

<span data-ttu-id="fb501-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="fb501-114">The type of the array elements.</span></span>