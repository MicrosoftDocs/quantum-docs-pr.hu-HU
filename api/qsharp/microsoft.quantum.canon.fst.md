---
uid: Microsoft.Quantum.Canon.Fst
title: FST függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840512"
---
# <a name="fst-function"></a><span data-ttu-id="8805a-102">FST függvény</span><span class="sxs-lookup"><span data-stu-id="8805a-102">Fst function</span></span>

<span data-ttu-id="8805a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8805a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8805a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8805a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8805a-105">Egy pár után visszaadja az első elemét.</span><span class="sxs-lookup"><span data-stu-id="8805a-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="8805a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8805a-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="8805a-107">pár: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="8805a-107">pair : ('T,'U)</span></span>

<span data-ttu-id="8805a-108">Két elemet tartalmazó rekord.</span><span class="sxs-lookup"><span data-stu-id="8805a-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="8805a-109">Kimenet: nem</span><span class="sxs-lookup"><span data-stu-id="8805a-109">Output : 'T</span></span>

<span data-ttu-id="8805a-110">A első eleme `pair` .</span><span class="sxs-lookup"><span data-stu-id="8805a-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8805a-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8805a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8805a-112">Nem</span><span class="sxs-lookup"><span data-stu-id="8805a-112">'T</span></span>

<span data-ttu-id="8805a-113">A pár első tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="8805a-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="8805a-114">' U</span><span class="sxs-lookup"><span data-stu-id="8805a-114">'U</span></span>

<span data-ttu-id="8805a-115">A pár második tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="8805a-115">The type of the pair's second member.</span></span>