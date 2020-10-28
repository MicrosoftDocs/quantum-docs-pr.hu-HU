---
uid: Microsoft.Quantum.Canon.Snd
title: Snd-függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715447"
---
# <a name="snd-function"></a><span data-ttu-id="94135-102">Snd-függvény</span><span class="sxs-lookup"><span data-stu-id="94135-102">Snd function</span></span>

<span data-ttu-id="94135-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94135-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94135-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94135-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94135-105">Egy pár után a a második elemet adja vissza.</span><span class="sxs-lookup"><span data-stu-id="94135-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="94135-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="94135-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="94135-107">pár: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="94135-107">pair : ('T,'U)</span></span>

<span data-ttu-id="94135-108">Két elemet tartalmazó rekord.</span><span class="sxs-lookup"><span data-stu-id="94135-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="94135-109">Kimenet: U</span><span class="sxs-lookup"><span data-stu-id="94135-109">Output : 'U</span></span>

<span data-ttu-id="94135-110">A második eleme `pair` .</span><span class="sxs-lookup"><span data-stu-id="94135-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="94135-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="94135-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94135-112">Nem</span><span class="sxs-lookup"><span data-stu-id="94135-112">'T</span></span>

<span data-ttu-id="94135-113">A pár első tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="94135-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="94135-114">' U</span><span class="sxs-lookup"><span data-stu-id="94135-114">'U</span></span>

<span data-ttu-id="94135-115">A pár második tagjának típusa.</span><span class="sxs-lookup"><span data-stu-id="94135-115">The type of the pair's second member.</span></span>