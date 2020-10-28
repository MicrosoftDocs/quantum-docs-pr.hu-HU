---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: ApplyCurriedOpCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: 4e57772bc5440a473c28279ac125170caaa120f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718313"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="edacd-102">ApplyCurriedOpCA művelet</span><span class="sxs-lookup"><span data-stu-id="edacd-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="edacd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="edacd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="edacd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="edacd-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="edacd-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="edacd-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="edacd-106">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="edacd-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="edacd-107">első: nem</span><span class="sxs-lookup"><span data-stu-id="edacd-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="edacd-108">második: ' U</span><span class="sxs-lookup"><span data-stu-id="edacd-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="edacd-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="edacd-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="edacd-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="edacd-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="edacd-111">Nem</span><span class="sxs-lookup"><span data-stu-id="edacd-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="edacd-112">' U</span><span class="sxs-lookup"><span data-stu-id="edacd-112">'U</span></span>

