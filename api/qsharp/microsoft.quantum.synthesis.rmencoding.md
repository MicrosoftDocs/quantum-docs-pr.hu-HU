---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: ef9be0f0628c8ba8c5f131cc558bdcda6bb6ea55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725475"
---
# <a name="rmencoding-function"></a><span data-ttu-id="35642-102">RMEncoding függvény</span><span class="sxs-lookup"><span data-stu-id="35642-102">RMEncoding function</span></span>

<span data-ttu-id="35642-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="35642-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="35642-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35642-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35642-105">{-1,1} Logikai igazság értékének kódolása</span><span class="sxs-lookup"><span data-stu-id="35642-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="35642-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="35642-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="35642-107">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="35642-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="35642-108">Logikai érték</span><span class="sxs-lookup"><span data-stu-id="35642-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="35642-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="35642-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="35642-110">1, ha `b` hamis, ellenkező esetben – 1</span><span class="sxs-lookup"><span data-stu-id="35642-110">1, if `b` is false, otherwise -1</span></span>