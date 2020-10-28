---
uid: Microsoft.Quantum.Canon.Fst
title: FST függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716188"
---
# <a name="fst-function"></a><span data-ttu-id="80bd1-102">FST függvény</span><span class="sxs-lookup"><span data-stu-id="80bd1-102">Fst function</span></span>

<span data-ttu-id="80bd1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80bd1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80bd1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80bd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80bd1-105">Egy pár után visszaadja az első elemét.</span><span class="sxs-lookup"><span data-stu-id="80bd1-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="80bd1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="80bd1-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="80bd1-107">pár: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="80bd1-107">pair : ('T,'U)</span></span>

<span data-ttu-id="80bd1-108">Két elemet tartalmazó rekord.</span><span class="sxs-lookup"><span data-stu-id="80bd1-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="80bd1-109">Kimenet: nem</span><span class="sxs-lookup"><span data-stu-id="80bd1-109">Output : 'T</span></span>

<span data-ttu-id="80bd1-110">A első eleme `pair` .</span><span class="sxs-lookup"><span data-stu-id="80bd1-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="80bd1-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="80bd1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80bd1-112">Nem</span><span class="sxs-lookup"><span data-stu-id="80bd1-112">'T</span></span>

<span data-ttu-id="80bd1-113">A pár első tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="80bd1-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="80bd1-114">' U</span><span class="sxs-lookup"><span data-stu-id="80bd1-114">'U</span></span>

<span data-ttu-id="80bd1-115">A pár második tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="80bd1-115">The type of the pair's second member.</span></span>