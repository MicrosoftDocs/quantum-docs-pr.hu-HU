---
uid: Microsoft.Quantum.Synthesis.RMEncoding
title: RMEncoding függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: RMEncoding
qsharp.summary: '{-1,1} coding of a Boolean truth value'
ms.openlocfilehash: f3c54d2e40511dacb21618b4eaf1eef9f4903f9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855332"
---
# <a name="rmencoding-function"></a><span data-ttu-id="e32f1-102">RMEncoding függvény</span><span class="sxs-lookup"><span data-stu-id="e32f1-102">RMEncoding function</span></span>

<span data-ttu-id="e32f1-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e32f1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e32f1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e32f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e32f1-105">{-1,1} Logikai igazság értékének kódolása</span><span class="sxs-lookup"><span data-stu-id="e32f1-105">{-1,1} coding of a Boolean truth value</span></span>

```qsharp
function RMEncoding (b : Bool) : Int
```


## <a name="input"></a><span data-ttu-id="e32f1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e32f1-106">Input</span></span>

### <a name="b--bool"></a><span data-ttu-id="e32f1-107">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e32f1-107">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e32f1-108">Logikai érték</span><span class="sxs-lookup"><span data-stu-id="e32f1-108">Boolean value</span></span>



## <a name="output--int"></a><span data-ttu-id="e32f1-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e32f1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e32f1-110">1, ha `b` hamis, ellenkező esetben – 1</span><span class="sxs-lookup"><span data-stu-id="e32f1-110">1, if `b` is false, otherwise -1</span></span>