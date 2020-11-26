---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.DelayCA
title: DelayCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: DelayCA
qsharp.summary: ''
ms.openlocfilehash: aacbf6fb595700cf0631263ddbc1925846f9ad9f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192587"
---
# <a name="delayca-operation"></a><span data-ttu-id="84d11-102">DelayCA művelet</span><span class="sxs-lookup"><span data-stu-id="84d11-102">DelayCA operation</span></span>

<span data-ttu-id="84d11-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="84d11-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="84d11-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="84d11-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="84d11-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="84d11-105">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="84d11-106">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="84d11-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="arg--t"></a><span data-ttu-id="84d11-107">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="84d11-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="84d11-108">AUX: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84d11-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="84d11-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84d11-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="84d11-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="84d11-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84d11-111">Nem</span><span class="sxs-lookup"><span data-stu-id="84d11-111">'T</span></span>

