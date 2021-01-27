---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: ApplyIfZeroC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: c4d1618ff5e2a3d61823eddd6905445effcecfdd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854187"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="ab026-102">ApplyIfZeroC művelet</span><span class="sxs-lookup"><span data-stu-id="ab026-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="ab026-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="ab026-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ab026-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ab026-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="ab026-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ab026-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="ab026-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="ab026-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="ab026-107">onResultZeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="ab026-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="ab026-108">zeroArg: nem</span><span class="sxs-lookup"><span data-stu-id="ab026-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="ab026-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab026-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ab026-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ab026-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab026-111">Nem</span><span class="sxs-lookup"><span data-stu-id="ab026-111">'T</span></span>

