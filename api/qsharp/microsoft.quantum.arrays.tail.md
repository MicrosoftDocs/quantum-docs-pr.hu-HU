---
uid: Microsoft.Quantum.Arrays.Tail
title: Farok függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845404"
---
# <a name="tail-function"></a><span data-ttu-id="2b8b5-102">Farok függvény</span><span class="sxs-lookup"><span data-stu-id="2b8b5-102">Tail function</span></span>

<span data-ttu-id="2b8b5-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2b8b5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2b8b5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b8b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b8b5-105">A tömb utolsó elemét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2b8b5-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="2b8b5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2b8b5-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="2b8b5-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="2b8b5-107">array : 'A[]</span></span>

<span data-ttu-id="2b8b5-108">Az a tömb, amelynek az utolsó elemét elvégezték.</span><span class="sxs-lookup"><span data-stu-id="2b8b5-108">Array of which the last element is taken.</span></span> <span data-ttu-id="2b8b5-109">A tömbnek legalább 1 karakterből kell állnia.</span><span class="sxs-lookup"><span data-stu-id="2b8b5-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="2b8b5-110">Kimenet: "A"</span><span class="sxs-lookup"><span data-stu-id="2b8b5-110">Output : 'A</span></span>

<span data-ttu-id="2b8b5-111">A tömb utolsó eleme.</span><span class="sxs-lookup"><span data-stu-id="2b8b5-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2b8b5-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2b8b5-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="2b8b5-113">"A</span><span class="sxs-lookup"><span data-stu-id="2b8b5-113">'A</span></span>

<span data-ttu-id="2b8b5-114">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="2b8b5-114">The type of the array elements.</span></span>