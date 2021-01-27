---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854879"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="57648-102">StateGenerator-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="57648-102">StateGenerator user defined type</span></span>

<span data-ttu-id="57648-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="57648-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="57648-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="57648-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="57648-105">Egy olyan műveletet ismertet, amely egy adott bemenetet készít elő egy szekvenciális osztályozó számára.</span><span class="sxs-lookup"><span data-stu-id="57648-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="57648-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="57648-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="57648-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57648-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57648-108">Azon qubits száma, amelyeken a kódolt bemenet definiálva van.</span><span class="sxs-lookup"><span data-stu-id="57648-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="57648-109">Előkészítés: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="57648-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="57648-110">Egy olyan művelet, amely előkészíti a kódolt bemenetet egy kis endian `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="57648-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>