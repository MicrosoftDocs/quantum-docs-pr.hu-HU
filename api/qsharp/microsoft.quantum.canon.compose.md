---
uid: Microsoft.Quantum.Canon.Compose
title: Összeállítási függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716496"
---
# <a name="compose-function"></a><span data-ttu-id="2e7dd-102">Összeállítási függvény</span><span class="sxs-lookup"><span data-stu-id="2e7dd-102">Compose function</span></span>

<span data-ttu-id="2e7dd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e7dd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e7dd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e7dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e7dd-105">Két függvény összeállítását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="2e7dd-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2e7dd-106">Description</span></span>

<span data-ttu-id="2e7dd-107">A $f $ és a $g $ függvényben a megadott függvények egy új függvényt adnak vissza, amely az $f \circ g $ értéket jelképezi.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="2e7dd-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2e7dd-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="2e7dd-109">külső: "U->" V</span><span class="sxs-lookup"><span data-stu-id="2e7dd-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="2e7dd-110">Az alkalmazni kívánt második függvény.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="2e7dd-111">belső: nem > U</span><span class="sxs-lookup"><span data-stu-id="2e7dd-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="2e7dd-112">Az elsőként alkalmazandó függvény.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="2e7dd-113">Kimenet: nem > ' V</span><span class="sxs-lookup"><span data-stu-id="2e7dd-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="2e7dd-114">Egy új függvény $h $, amely minden bemenethez $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2e7dd-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2e7dd-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e7dd-116">Nem</span><span class="sxs-lookup"><span data-stu-id="2e7dd-116">'T</span></span>

<span data-ttu-id="2e7dd-117">Az elsőként alkalmazandó függvény bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="2e7dd-118">' U</span><span class="sxs-lookup"><span data-stu-id="2e7dd-118">'U</span></span>

<span data-ttu-id="2e7dd-119">Az elsőként alkalmazandó függvény kimeneti típusa és az alkalmazandó második függvény bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="2e7dd-120">"V</span><span class="sxs-lookup"><span data-stu-id="2e7dd-120">'V</span></span>

<span data-ttu-id="2e7dd-121">Az alkalmazni kívánt második függvény kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="2e7dd-121">The output type of the second function to be applied.</span></span>