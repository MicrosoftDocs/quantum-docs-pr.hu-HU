---
uid: Microsoft.Quantum.Canon.Snd
title: Snd-függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852152"
---
# <a name="snd-function"></a><span data-ttu-id="2fd6c-102">Snd-függvény</span><span class="sxs-lookup"><span data-stu-id="2fd6c-102">Snd function</span></span>

<span data-ttu-id="2fd6c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2fd6c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2fd6c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fd6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fd6c-105">Egy pár után a a második elemet adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2fd6c-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="2fd6c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2fd6c-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="2fd6c-107">pár: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="2fd6c-107">pair : ('T,'U)</span></span>

<span data-ttu-id="2fd6c-108">Két elemet tartalmazó rekord.</span><span class="sxs-lookup"><span data-stu-id="2fd6c-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="2fd6c-109">Kimenet: U</span><span class="sxs-lookup"><span data-stu-id="2fd6c-109">Output : 'U</span></span>

<span data-ttu-id="2fd6c-110">A második eleme `pair` .</span><span class="sxs-lookup"><span data-stu-id="2fd6c-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2fd6c-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2fd6c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2fd6c-112">Nem</span><span class="sxs-lookup"><span data-stu-id="2fd6c-112">'T</span></span>

<span data-ttu-id="2fd6c-113">A pár első tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="2fd6c-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="2fd6c-114">' U</span><span class="sxs-lookup"><span data-stu-id="2fd6c-114">'U</span></span>

<span data-ttu-id="2fd6c-115">A pár második tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="2fd6c-115">The type of the pair's second member.</span></span>