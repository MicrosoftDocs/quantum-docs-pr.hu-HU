---
uid: Microsoft.Quantum.Arrays.Head
title: Head függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848574"
---
# <a name="head-function"></a><span data-ttu-id="c8d0f-102">Head függvény</span><span class="sxs-lookup"><span data-stu-id="c8d0f-102">Head function</span></span>

<span data-ttu-id="c8d0f-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c8d0f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c8d0f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8d0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8d0f-105">A tömb első elemét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c8d0f-105">Returns the first element of the array.</span></span>

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="c8d0f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c8d0f-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="c8d0f-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="c8d0f-107">array : 'A[]</span></span>

<span data-ttu-id="c8d0f-108">Az első elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="c8d0f-108">Array of which the first element is taken.</span></span> <span data-ttu-id="c8d0f-109">A tömbnek legalább 1 karakterből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="c8d0f-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="c8d0f-110">Kimenet: "A"</span><span class="sxs-lookup"><span data-stu-id="c8d0f-110">Output : 'A</span></span>

<span data-ttu-id="c8d0f-111">A tömb első eleme.</span><span class="sxs-lookup"><span data-stu-id="c8d0f-111">The first element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c8d0f-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c8d0f-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="c8d0f-113">"A</span><span class="sxs-lookup"><span data-stu-id="c8d0f-113">'A</span></span>

<span data-ttu-id="c8d0f-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="c8d0f-114">The type of the array elements.</span></span>