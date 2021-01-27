---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Kódolt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855482"
---
# <a name="encoded-function"></a><span data-ttu-id="47a66-102">Kódolt függvény</span><span class="sxs-lookup"><span data-stu-id="47a66-102">Encoded function</span></span>

<span data-ttu-id="47a66-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="47a66-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="47a66-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47a66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47a66-105">Az igazság tábla kódolása {1,-1} kódolással</span><span class="sxs-lookup"><span data-stu-id="47a66-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="47a66-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="47a66-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="47a66-107">tábla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="47a66-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="47a66-108">Igazság tábla az igazság értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="47a66-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="47a66-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="47a66-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="47a66-110">Igazság tábla egész számok tömbje {1,-1}</span><span class="sxs-lookup"><span data-stu-id="47a66-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="47a66-111">Példa</span><span class="sxs-lookup"><span data-stu-id="47a66-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```