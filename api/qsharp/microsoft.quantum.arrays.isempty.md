---
uid: Microsoft.Quantum.Arrays.IsEmpty
title: IsEmpty függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsEmpty
qsharp.summary: Returns true if and only if an array is empty.
ms.openlocfilehash: ae3ad8763987bab9fdae07a5fe9bd4aabef65205
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220977"
---
# <a name="isempty-function"></a><span data-ttu-id="02ae4-102">IsEmpty függvény</span><span class="sxs-lookup"><span data-stu-id="02ae4-102">IsEmpty function</span></span>

<span data-ttu-id="02ae4-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="02ae4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="02ae4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02ae4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02ae4-105">Igaz értéket ad vissza, és csak akkor, ha egy tömb üres.</span><span class="sxs-lookup"><span data-stu-id="02ae4-105">Returns true if and only if an array is empty.</span></span>

```qsharp
function IsEmpty<'T> (array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="02ae4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="02ae4-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="02ae4-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="02ae4-107">array : 'T[]</span></span>

<span data-ttu-id="02ae4-108">Az ellenőrizendő tömb.</span><span class="sxs-lookup"><span data-stu-id="02ae4-108">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="02ae4-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="02ae4-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="02ae4-110">`true` Ha és csak akkor, ha a tömb üres (a hossza 0).</span><span class="sxs-lookup"><span data-stu-id="02ae4-110">`true` if and only if the array is empty (has length 0).</span></span>

## <a name="type-parameters"></a><span data-ttu-id="02ae4-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="02ae4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02ae4-112">Nem</span><span class="sxs-lookup"><span data-stu-id="02ae4-112">'T</span></span>

