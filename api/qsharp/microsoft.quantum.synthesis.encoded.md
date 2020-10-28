---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kódolt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725208"
---
# <a name="encoded-function"></a><span data-ttu-id="49103-102">Kódolt függvény</span><span class="sxs-lookup"><span data-stu-id="49103-102">Encoded function</span></span>

<span data-ttu-id="49103-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="49103-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="49103-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49103-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49103-105">Az igazság tábla kódolása {1,-1} kódolással</span><span class="sxs-lookup"><span data-stu-id="49103-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="49103-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="49103-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="49103-107">tábla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="49103-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="49103-108">Igazság tábla az igazság értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="49103-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="49103-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="49103-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="49103-110">Igazság tábla egész számok tömbje {1,-1}</span><span class="sxs-lookup"><span data-stu-id="49103-110">Truth table as array of {1,-1} integers</span></span>