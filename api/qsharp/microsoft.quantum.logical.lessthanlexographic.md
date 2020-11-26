---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197670"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="901cf-102">LessThanLexographic függvény</span><span class="sxs-lookup"><span data-stu-id="901cf-102">LessThanLexographic function</span></span>

<span data-ttu-id="901cf-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="901cf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="901cf-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="901cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="901cf-105">A megvalósításához használatos `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="901cf-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="901cf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="901cf-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="901cf-107">összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="901cf-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="901cf-108">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="901cf-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="901cf-109">jobb: 'T []</span><span class="sxs-lookup"><span data-stu-id="901cf-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="901cf-110">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="901cf-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="901cf-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="901cf-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="901cf-112">Nem</span><span class="sxs-lookup"><span data-stu-id="901cf-112">'T</span></span>

