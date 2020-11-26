---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: ApplyIfZeroC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230837"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="92628-102">ApplyIfZeroC művelet</span><span class="sxs-lookup"><span data-stu-id="92628-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="92628-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="92628-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="92628-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="92628-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="92628-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="92628-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="92628-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="92628-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="92628-107">onResultZeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="92628-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="92628-108">zeroArg: nem</span><span class="sxs-lookup"><span data-stu-id="92628-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="92628-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92628-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="92628-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="92628-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="92628-111">Nem</span><span class="sxs-lookup"><span data-stu-id="92628-111">'T</span></span>

