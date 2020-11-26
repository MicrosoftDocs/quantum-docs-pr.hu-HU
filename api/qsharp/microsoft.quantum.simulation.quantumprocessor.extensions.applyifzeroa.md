---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: ApplyIfZeroA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: d57f07beddc94d11a2143ba5d1fd975760260731
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230871"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="9a2b2-102">ApplyIfZeroA művelet</span><span class="sxs-lookup"><span data-stu-id="9a2b2-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="9a2b2-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="9a2b2-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="9a2b2-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9a2b2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9a2b2-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9a2b2-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="9a2b2-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="9a2b2-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="9a2b2-107">onResultZeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a2b2-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="9a2b2-108">zeroArg: nem</span><span class="sxs-lookup"><span data-stu-id="9a2b2-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="9a2b2-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a2b2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a2b2-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9a2b2-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a2b2-111">Nem</span><span class="sxs-lookup"><span data-stu-id="9a2b2-111">'T</span></span>

