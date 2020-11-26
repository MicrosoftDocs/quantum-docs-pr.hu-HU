---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: faca9b3f6d9a132b591a532c9e2ce54af1f0b182
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218937"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="7fbf7-102">ApplyCurriedOpC művelet</span><span class="sxs-lookup"><span data-stu-id="7fbf7-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="7fbf7-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7fbf7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7fbf7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7fbf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7fbf7-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7fbf7-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="7fbf7-106">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="7fbf7-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="7fbf7-107">első: nem</span><span class="sxs-lookup"><span data-stu-id="7fbf7-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="7fbf7-108">második: ' U</span><span class="sxs-lookup"><span data-stu-id="7fbf7-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7fbf7-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7fbf7-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7fbf7-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7fbf7-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7fbf7-111">Nem</span><span class="sxs-lookup"><span data-stu-id="7fbf7-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="7fbf7-112">' U</span><span class="sxs-lookup"><span data-stu-id="7fbf7-112">'U</span></span>

