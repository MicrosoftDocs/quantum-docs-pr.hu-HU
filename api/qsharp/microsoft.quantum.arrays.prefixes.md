---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Előtagok függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845512"
---
# <a name="prefixes-function"></a><span data-ttu-id="b0d67-102">Előtagok függvény</span><span class="sxs-lookup"><span data-stu-id="b0d67-102">Prefixes function</span></span>

<span data-ttu-id="b0d67-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b0d67-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b0d67-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0d67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0d67-105">A tömb megadott értéke az összes előtagjait adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b0d67-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="b0d67-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b0d67-106">Description</span></span>

<span data-ttu-id="b0d67-107">Az összes előtag tömbjét adja vissza, amely egy olyan tömbtől kezdődik, amely csak az első elemet tartalmazza, amíg a teljes tömb be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="b0d67-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="b0d67-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b0d67-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="b0d67-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="b0d67-109">array : 'T[]</span></span>

<span data-ttu-id="b0d67-110">Elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="b0d67-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b0d67-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="b0d67-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b0d67-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b0d67-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b0d67-113">Nem</span><span class="sxs-lookup"><span data-stu-id="b0d67-113">'T</span></span>

<span data-ttu-id="b0d67-114">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="b0d67-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="b0d67-115">Példa</span><span class="sxs-lookup"><span data-stu-id="b0d67-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```