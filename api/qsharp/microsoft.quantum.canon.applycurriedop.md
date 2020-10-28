---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: 22e2ace51175ed9df1c70bf75ce2b497f8449020
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718337"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="eccc9-102">ApplyCurriedOp művelet</span><span class="sxs-lookup"><span data-stu-id="eccc9-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="eccc9-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eccc9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eccc9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eccc9-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="eccc9-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eccc9-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="eccc9-106">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eccc9-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="eccc9-107">első: nem</span><span class="sxs-lookup"><span data-stu-id="eccc9-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="eccc9-108">második: ' U</span><span class="sxs-lookup"><span data-stu-id="eccc9-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="eccc9-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eccc9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eccc9-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="eccc9-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eccc9-111">Nem</span><span class="sxs-lookup"><span data-stu-id="eccc9-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="eccc9-112">' U</span><span class="sxs-lookup"><span data-stu-id="eccc9-112">'U</span></span>

