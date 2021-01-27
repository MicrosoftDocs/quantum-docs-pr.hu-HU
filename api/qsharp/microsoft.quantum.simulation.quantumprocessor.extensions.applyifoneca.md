---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: ApplyIfOneCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: 8dd2d501d4598b1de69daa87f7a0941262b7d435
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858912"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="c4189-102">ApplyIfOneCA művelet</span><span class="sxs-lookup"><span data-stu-id="c4189-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="c4189-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c4189-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c4189-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c4189-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c4189-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c4189-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="c4189-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="c4189-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj--ctl"></a><span data-ttu-id="c4189-107">onResultOneOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c4189-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="c4189-108">oneArg: nem</span><span class="sxs-lookup"><span data-stu-id="c4189-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="c4189-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4189-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c4189-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c4189-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4189-111">Nem</span><span class="sxs-lookup"><span data-stu-id="c4189-111">'T</span></span>

