---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingFromBEandQubit
title: ApplyBlockEncodingFromBEandQubit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingFromBEandQubit
qsharp.summary: Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding
ms.openlocfilehash: d11c5bd8a33fc5dfc9ed3aa374c9c53afe286e24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722101"
---
# <a name="applyblockencodingfrombeandqubit-operation"></a><span data-ttu-id="9a2a2-102">ApplyBlockEncodingFromBEandQubit művelet</span><span class="sxs-lookup"><span data-stu-id="9a2a2-102">ApplyBlockEncodingFromBEandQubit operation</span></span>

<span data-ttu-id="9a2a2-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9a2a2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9a2a2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a2a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a2a2-105">A ((LittleEndian, Qubit []) => () a következő átalakítása: BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="9a2a2-105">Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding</span></span>

```qsharp
operation ApplyBlockEncodingFromBEandQubit (op : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl), auxiliary : Qubit[], system : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9a2a2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9a2a2-106">Input</span></span>

### <a name="op--littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="9a2a2-107">op: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9a2a2-107">op : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="9a2a2-108">kiegészítő: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9a2a2-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="system--qubit"></a><span data-ttu-id="9a2a2-109">System: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9a2a2-109">system : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="9a2a2-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a2a2-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

