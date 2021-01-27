---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: f7dd30171acd3786c6d012b82b9abf99f9042caf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858257"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="32ba1-102">ApplyIfZeroCA művelet</span><span class="sxs-lookup"><span data-stu-id="32ba1-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="32ba1-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="32ba1-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="32ba1-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="32ba1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="32ba1-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="32ba1-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="32ba1-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="32ba1-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="32ba1-107">onResultZeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="32ba1-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="32ba1-108">zeroArg: nem</span><span class="sxs-lookup"><span data-stu-id="32ba1-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="32ba1-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32ba1-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="32ba1-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="32ba1-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="32ba1-111">Nem</span><span class="sxs-lookup"><span data-stu-id="32ba1-111">'T</span></span>

