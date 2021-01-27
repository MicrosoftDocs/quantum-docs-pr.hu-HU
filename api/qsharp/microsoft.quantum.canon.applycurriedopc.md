---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 65e861914b57cf8a32f2321f881248830b72c54e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841907"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="dd6e9-102">ApplyCurriedOpC művelet</span><span class="sxs-lookup"><span data-stu-id="dd6e9-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="dd6e9-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd6e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd6e9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd6e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="dd6e9-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dd6e9-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="dd6e9-106">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="dd6e9-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="dd6e9-107">első: nem</span><span class="sxs-lookup"><span data-stu-id="dd6e9-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="dd6e9-108">második: ' U</span><span class="sxs-lookup"><span data-stu-id="dd6e9-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="dd6e9-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd6e9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dd6e9-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dd6e9-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dd6e9-111">Nem</span><span class="sxs-lookup"><span data-stu-id="dd6e9-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="dd6e9-112">' U</span><span class="sxs-lookup"><span data-stu-id="dd6e9-112">'U</span></span>

