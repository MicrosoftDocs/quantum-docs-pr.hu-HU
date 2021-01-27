---
uid: Microsoft.Quantum.Canon.Compose
title: Összeállítási függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840911"
---
# <a name="compose-function"></a><span data-ttu-id="013f9-102">Összeállítási függvény</span><span class="sxs-lookup"><span data-stu-id="013f9-102">Compose function</span></span>

<span data-ttu-id="013f9-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="013f9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="013f9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="013f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="013f9-105">Két függvény összeállítását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="013f9-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="013f9-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="013f9-106">Description</span></span>

<span data-ttu-id="013f9-107">A $f $ és a $g $ függvényben a megadott függvények egy új függvényt adnak vissza, amely az $f \circ g $ értéket jelképezi.</span><span class="sxs-lookup"><span data-stu-id="013f9-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="013f9-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="013f9-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="013f9-109">külső: "U->" V</span><span class="sxs-lookup"><span data-stu-id="013f9-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="013f9-110">Az alkalmazni kívánt második függvény.</span><span class="sxs-lookup"><span data-stu-id="013f9-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="013f9-111">belső: nem > U</span><span class="sxs-lookup"><span data-stu-id="013f9-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="013f9-112">Az elsőként alkalmazandó függvény.</span><span class="sxs-lookup"><span data-stu-id="013f9-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="013f9-113">Kimenet: nem > ' V</span><span class="sxs-lookup"><span data-stu-id="013f9-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="013f9-114">Egy új függvény $h $, amely minden bemenethez $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="013f9-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="013f9-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="013f9-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="013f9-116">Nem</span><span class="sxs-lookup"><span data-stu-id="013f9-116">'T</span></span>

<span data-ttu-id="013f9-117">Az elsőként alkalmazandó függvény bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="013f9-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="013f9-118">' U</span><span class="sxs-lookup"><span data-stu-id="013f9-118">'U</span></span>

<span data-ttu-id="013f9-119">Az elsőként alkalmazandó függvény kimeneti típusa és az alkalmazandó második függvény bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="013f9-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="013f9-120">"V</span><span class="sxs-lookup"><span data-stu-id="013f9-120">'V</span></span>

<span data-ttu-id="013f9-121">Az alkalmazni kívánt második függvény kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="013f9-121">The output type of the second function to be applied.</span></span>