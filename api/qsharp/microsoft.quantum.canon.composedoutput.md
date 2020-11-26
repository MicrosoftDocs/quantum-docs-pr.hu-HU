---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207462"
---
# <a name="composedoutput-function"></a><span data-ttu-id="e35aa-102">ComposedOutput függvény</span><span class="sxs-lookup"><span data-stu-id="e35aa-102">ComposedOutput function</span></span>

<span data-ttu-id="e35aa-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e35aa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e35aa-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e35aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e35aa-105">`inner`Egy adott bemenethez tartozó összeállítás kimenetét adja vissza `outer` .</span><span class="sxs-lookup"><span data-stu-id="e35aa-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="e35aa-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e35aa-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="e35aa-107">külső: "U->" V</span><span class="sxs-lookup"><span data-stu-id="e35aa-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="e35aa-108">belső: nem > U</span><span class="sxs-lookup"><span data-stu-id="e35aa-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="e35aa-109">cél: nem</span><span class="sxs-lookup"><span data-stu-id="e35aa-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="e35aa-110">Kimenet: "V</span><span class="sxs-lookup"><span data-stu-id="e35aa-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e35aa-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e35aa-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e35aa-112">Nem</span><span class="sxs-lookup"><span data-stu-id="e35aa-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="e35aa-113">' U</span><span class="sxs-lookup"><span data-stu-id="e35aa-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="e35aa-114">"V</span><span class="sxs-lookup"><span data-stu-id="e35aa-114">'V</span></span>

