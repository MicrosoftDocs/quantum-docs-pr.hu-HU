---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722395"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="2488a-102">StateGenerator-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="2488a-102">StateGenerator user defined type</span></span>

<span data-ttu-id="2488a-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2488a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2488a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2488a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2488a-105">Egy olyan műveletet ismertet, amely egy adott bemenetet készít elő egy szekvenciális osztályozó számára.</span><span class="sxs-lookup"><span data-stu-id="2488a-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="2488a-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="2488a-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2488a-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2488a-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2488a-108">Azon qubits száma, amelyeken a kódolt bemenet definiálva van.</span><span class="sxs-lookup"><span data-stu-id="2488a-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="2488a-109">Előkészítés: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) - => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2488a-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2488a-110">Egy olyan művelet, amely előkészíti a kódolt bemenetet egy kis endian `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="2488a-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>