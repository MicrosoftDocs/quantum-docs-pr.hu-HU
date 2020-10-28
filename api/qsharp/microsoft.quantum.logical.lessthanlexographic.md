---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709959"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="16099-102">LessThanLexographic függvény</span><span class="sxs-lookup"><span data-stu-id="16099-102">LessThanLexographic function</span></span>

<span data-ttu-id="16099-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="16099-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="16099-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16099-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16099-105">A megvalósításához használatos `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="16099-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="16099-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="16099-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="16099-107">összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16099-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="16099-108">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="16099-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="16099-109">jobb: 'T []</span><span class="sxs-lookup"><span data-stu-id="16099-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="16099-110">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="16099-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="16099-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="16099-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16099-112">Nem</span><span class="sxs-lookup"><span data-stu-id="16099-112">'T</span></span>

