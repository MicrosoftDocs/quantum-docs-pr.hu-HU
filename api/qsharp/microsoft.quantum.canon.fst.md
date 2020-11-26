---
uid: Microsoft.Quantum.Canon.Fst
title: FST függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206935"
---
# <a name="fst-function"></a><span data-ttu-id="3da63-102">FST függvény</span><span class="sxs-lookup"><span data-stu-id="3da63-102">Fst function</span></span>

<span data-ttu-id="3da63-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3da63-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3da63-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3da63-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3da63-105">Egy pár után visszaadja az első elemét.</span><span class="sxs-lookup"><span data-stu-id="3da63-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="3da63-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3da63-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="3da63-107">pár: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="3da63-107">pair : ('T,'U)</span></span>

<span data-ttu-id="3da63-108">Két elemet tartalmazó rekord.</span><span class="sxs-lookup"><span data-stu-id="3da63-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="3da63-109">Kimenet: nem</span><span class="sxs-lookup"><span data-stu-id="3da63-109">Output : 'T</span></span>

<span data-ttu-id="3da63-110">A első eleme `pair` .</span><span class="sxs-lookup"><span data-stu-id="3da63-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3da63-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3da63-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3da63-112">Nem</span><span class="sxs-lookup"><span data-stu-id="3da63-112">'T</span></span>

<span data-ttu-id="3da63-113">A pár első tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="3da63-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="3da63-114">' U</span><span class="sxs-lookup"><span data-stu-id="3da63-114">'U</span></span>

<span data-ttu-id="3da63-115">A pár második tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="3da63-115">The type of the pair's second member.</span></span>