---
uid: Microsoft.Quantum.Arrays.Merged
title: Egyesített függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719009"
---
# <a name="merged-function"></a><span data-ttu-id="b9961-102">Egyesített függvény</span><span class="sxs-lookup"><span data-stu-id="b9961-102">Merged function</span></span>

<span data-ttu-id="b9961-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b9961-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b9961-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9961-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9961-105">A két rendezett tömböt tartalmazó tömb egyetlen tömböt ad vissza, amely a sorrend sorrendjét egyaránt tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b9961-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="b9961-106">Belsőleg használatos egyesítés szerint.</span><span class="sxs-lookup"><span data-stu-id="b9961-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b9961-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b9961-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="b9961-108">összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b9961-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="b9961-109">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="b9961-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="b9961-110">jobb: 'T []</span><span class="sxs-lookup"><span data-stu-id="b9961-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="b9961-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="b9961-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b9961-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b9961-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b9961-113">Nem</span><span class="sxs-lookup"><span data-stu-id="b9961-113">'T</span></span>

