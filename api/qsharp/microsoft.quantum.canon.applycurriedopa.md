---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218954"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="ccbda-102">ApplyCurriedOpA művelet</span><span class="sxs-lookup"><span data-stu-id="ccbda-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="ccbda-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ccbda-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ccbda-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccbda-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ccbda-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ccbda-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="ccbda-106">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccbda-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="ccbda-107">első: nem</span><span class="sxs-lookup"><span data-stu-id="ccbda-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="ccbda-108">második: ' U</span><span class="sxs-lookup"><span data-stu-id="ccbda-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ccbda-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccbda-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ccbda-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ccbda-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ccbda-111">Nem</span><span class="sxs-lookup"><span data-stu-id="ccbda-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="ccbda-112">' U</span><span class="sxs-lookup"><span data-stu-id="ccbda-112">'U</span></span>

