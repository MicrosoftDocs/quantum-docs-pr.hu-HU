---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kódolt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203178"
---
# <a name="encoded-function"></a><span data-ttu-id="d405c-102">Kódolt függvény</span><span class="sxs-lookup"><span data-stu-id="d405c-102">Encoded function</span></span>

<span data-ttu-id="d405c-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d405c-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d405c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d405c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d405c-105">Az igazság tábla kódolása {1,-1} kódolással</span><span class="sxs-lookup"><span data-stu-id="d405c-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="d405c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d405c-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="d405c-107">tábla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d405c-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d405c-108">Igazság tábla az igazság értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="d405c-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="d405c-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d405c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d405c-110">Igazság tábla egész számok tömbje {1,-1}</span><span class="sxs-lookup"><span data-stu-id="d405c-110">Truth table as array of {1,-1} integers</span></span>