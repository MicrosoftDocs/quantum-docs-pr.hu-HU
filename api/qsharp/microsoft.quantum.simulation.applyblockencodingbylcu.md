---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852827"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="2bab3-102">ApplyBlockEncodingByLCU művelet</span><span class="sxs-lookup"><span data-stu-id="2bab3-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="2bab3-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2bab3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2bab3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2bab3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2bab3-105">A implementálása `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="2bab3-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2bab3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2bab3-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="2bab3-107">statePreparation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2bab3-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="2bab3-108">választó: ('T, 'S) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2bab3-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="2bab3-109">kiegészítő: nem</span><span class="sxs-lookup"><span data-stu-id="2bab3-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="2bab3-110">System: 'S</span><span class="sxs-lookup"><span data-stu-id="2bab3-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="2bab3-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2bab3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2bab3-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2bab3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2bab3-113">Nem</span><span class="sxs-lookup"><span data-stu-id="2bab3-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="2bab3-114">Képgalériája</span><span class="sxs-lookup"><span data-stu-id="2bab3-114">'S</span></span>

