---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: fc1cf50b7befd40cf20720032329438715a9b856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720185"
---
# <a name="applyconditionallyc-operation"></a><span data-ttu-id="7b97c-102">ApplyConditionallyC művelet</span><span class="sxs-lookup"><span data-stu-id="7b97c-102">ApplyConditionallyC operation</span></span>

<span data-ttu-id="7b97c-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7b97c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7b97c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b97c-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="7b97c-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7b97c-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="7b97c-106">measurementResults: __érvénytelen <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="7b97c-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="7b97c-107">resultsValues: __érvénytelen <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="7b97c-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-ctl"></a><span data-ttu-id="7b97c-108">onEqualOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7b97c-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="7b97c-109">equalArg: nem</span><span class="sxs-lookup"><span data-stu-id="7b97c-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-ctl"></a><span data-ttu-id="7b97c-110">onNonEqualOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7b97c-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="7b97c-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="7b97c-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7b97c-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b97c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b97c-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7b97c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b97c-114">Nem</span><span class="sxs-lookup"><span data-stu-id="7b97c-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="7b97c-115">' U</span><span class="sxs-lookup"><span data-stu-id="7b97c-115">'U</span></span>

