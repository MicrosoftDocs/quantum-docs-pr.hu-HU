---
uid: Microsoft.Quantum.Arrays.Tail
title: Farok függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220093"
---
# <a name="tail-function"></a><span data-ttu-id="bb365-102">Farok függvény</span><span class="sxs-lookup"><span data-stu-id="bb365-102">Tail function</span></span>

<span data-ttu-id="bb365-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bb365-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bb365-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb365-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb365-105">A tömb utolsó elemét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="bb365-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="bb365-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bb365-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="bb365-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="bb365-107">array : 'A[]</span></span>

<span data-ttu-id="bb365-108">Az a tömb, amelynek az utolsó elemét elvégezték.</span><span class="sxs-lookup"><span data-stu-id="bb365-108">Array of which the last element is taken.</span></span> <span data-ttu-id="bb365-109">A tömbnek legalább 1 karakterből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="bb365-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="bb365-110">Kimenet: "A"</span><span class="sxs-lookup"><span data-stu-id="bb365-110">Output : 'A</span></span>

<span data-ttu-id="bb365-111">A tömb utolsó eleme.</span><span class="sxs-lookup"><span data-stu-id="bb365-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bb365-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bb365-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="bb365-113">"A</span><span class="sxs-lookup"><span data-stu-id="bb365-113">'A</span></span>

<span data-ttu-id="bb365-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="bb365-114">The type of the array elements.</span></span>