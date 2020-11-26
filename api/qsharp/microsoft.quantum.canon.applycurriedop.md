---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: ab652159fa64a95401d07998ed4aaae5c4dbb92e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219022"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="ff1a4-102">ApplyCurriedOp művelet</span><span class="sxs-lookup"><span data-stu-id="ff1a4-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="ff1a4-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ff1a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ff1a4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff1a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="ff1a4-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ff1a4-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="ff1a4-106">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff1a4-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="ff1a4-107">első: nem</span><span class="sxs-lookup"><span data-stu-id="ff1a4-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="ff1a4-108">második: ' U</span><span class="sxs-lookup"><span data-stu-id="ff1a4-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ff1a4-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff1a4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ff1a4-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ff1a4-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ff1a4-111">Nem</span><span class="sxs-lookup"><span data-stu-id="ff1a4-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="ff1a4-112">' U</span><span class="sxs-lookup"><span data-stu-id="ff1a4-112">'U</span></span>

