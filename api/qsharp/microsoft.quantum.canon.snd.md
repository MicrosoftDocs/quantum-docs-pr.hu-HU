---
uid: Microsoft.Quantum.Canon.Snd
title: Snd-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205320"
---
# <a name="snd-function"></a><span data-ttu-id="af368-102">Snd-függvény</span><span class="sxs-lookup"><span data-stu-id="af368-102">Snd function</span></span>

<span data-ttu-id="af368-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="af368-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="af368-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af368-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af368-105">Egy pár után a a második elemet adja vissza.</span><span class="sxs-lookup"><span data-stu-id="af368-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="af368-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="af368-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="af368-107">pár: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="af368-107">pair : ('T,'U)</span></span>

<span data-ttu-id="af368-108">Két elemet tartalmazó rekord.</span><span class="sxs-lookup"><span data-stu-id="af368-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="af368-109">Kimenet: U</span><span class="sxs-lookup"><span data-stu-id="af368-109">Output : 'U</span></span>

<span data-ttu-id="af368-110">A második eleme `pair` .</span><span class="sxs-lookup"><span data-stu-id="af368-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="af368-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="af368-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af368-112">Nem</span><span class="sxs-lookup"><span data-stu-id="af368-112">'T</span></span>

<span data-ttu-id="af368-113">A pár első tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="af368-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="af368-114">' U</span><span class="sxs-lookup"><span data-stu-id="af368-114">'U</span></span>

<span data-ttu-id="af368-115">A pár második tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="af368-115">The type of the pair's second member.</span></span>