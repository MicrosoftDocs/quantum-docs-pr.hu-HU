---
uid: Microsoft.Quantum.Arrays.Merged
title: Egyesített függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845606"
---
# <a name="merged-function"></a><span data-ttu-id="47c0b-102">Egyesített függvény</span><span class="sxs-lookup"><span data-stu-id="47c0b-102">Merged function</span></span>

<span data-ttu-id="47c0b-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="47c0b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="47c0b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47c0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47c0b-105">A két rendezett tömböt tartalmazó tömb egyetlen tömböt ad vissza, amely a sorrend sorrendjét egyaránt tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="47c0b-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="47c0b-106">Belsőleg használatos egyesítés szerint.</span><span class="sxs-lookup"><span data-stu-id="47c0b-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="47c0b-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="47c0b-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="47c0b-108">összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="47c0b-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="47c0b-109">balra: nem []</span><span class="sxs-lookup"><span data-stu-id="47c0b-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="47c0b-110">jobb: 'T []</span><span class="sxs-lookup"><span data-stu-id="47c0b-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="47c0b-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="47c0b-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="47c0b-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="47c0b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47c0b-113">Nem</span><span class="sxs-lookup"><span data-stu-id="47c0b-113">'T</span></span>

