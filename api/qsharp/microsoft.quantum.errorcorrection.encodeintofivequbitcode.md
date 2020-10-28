---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712395"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="0f853-102">EncodeIntoFiveQubitCode művelet</span><span class="sxs-lookup"><span data-stu-id="0f853-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="0f853-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0f853-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0f853-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f853-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f853-105">Kódolja a ⟦ 5, 1, 3 ⟧ Quantum Code-ba.</span><span class="sxs-lookup"><span data-stu-id="0f853-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="0f853-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0f853-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="0f853-107">physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0f853-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0f853-108">Egy qubit, amely nem kódolt állapotot jelöl.</span><span class="sxs-lookup"><span data-stu-id="0f853-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="0f853-109">A tömb `Qubit[]` hossza 1.</span><span class="sxs-lookup"><span data-stu-id="0f853-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="0f853-110">auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0f853-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0f853-111">A kódolt állapotot jelölő kiegészítő qubits regisztere.</span><span class="sxs-lookup"><span data-stu-id="0f853-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="0f853-112">Kimenet: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="0f853-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="0f853-113">`LogicalRegister`A kódolt állapotot tároló fizikai qubits tömbje.</span><span class="sxs-lookup"><span data-stu-id="0f853-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f853-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0f853-114">See Also</span></span>

- [<span data-ttu-id="0f853-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="0f853-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)