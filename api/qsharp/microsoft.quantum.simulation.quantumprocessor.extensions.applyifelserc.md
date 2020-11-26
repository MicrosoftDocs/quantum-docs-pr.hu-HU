---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: ApplyIfElseRC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 33b3adfca87410480108eafd090632006117f7b2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192638"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="2e71b-102">ApplyIfElseRC művelet</span><span class="sxs-lookup"><span data-stu-id="2e71b-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="2e71b-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="2e71b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="2e71b-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2e71b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="2e71b-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2e71b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="2e71b-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e71b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="2e71b-107">onResultZeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="2e71b-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="2e71b-108">zeroArg: nem</span><span class="sxs-lookup"><span data-stu-id="2e71b-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-ctl"></a><span data-ttu-id="2e71b-109">onResultOneOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="2e71b-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="2e71b-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="2e71b-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="2e71b-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e71b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2e71b-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2e71b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e71b-113">Nem</span><span class="sxs-lookup"><span data-stu-id="2e71b-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="2e71b-114">' U</span><span class="sxs-lookup"><span data-stu-id="2e71b-114">'U</span></span>

