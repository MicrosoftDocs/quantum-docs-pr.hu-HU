---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 70e52b7440dca1fa8761db13d6187cb6bf8c43c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200985"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="d0027-102">EncodeIntoFiveQubitCode művelet</span><span class="sxs-lookup"><span data-stu-id="d0027-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="d0027-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d0027-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d0027-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0027-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0027-105">Kódolja a ⟦ 5, 1, 3 ⟧ Quantum Code-ba.</span><span class="sxs-lookup"><span data-stu-id="d0027-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="d0027-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d0027-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="d0027-107">physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d0027-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d0027-108">Egy qubit, amely nem kódolt állapotot jelöl.</span><span class="sxs-lookup"><span data-stu-id="d0027-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="d0027-109">A tömb `Qubit[]` hossza 1.</span><span class="sxs-lookup"><span data-stu-id="d0027-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="d0027-110">auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d0027-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d0027-111">A kódolt állapotot jelölő kiegészítő qubits regisztere.</span><span class="sxs-lookup"><span data-stu-id="d0027-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="d0027-112">Kimenet: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="d0027-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="d0027-113">`LogicalRegister`A kódolt állapotot tároló fizikai qubits tömbje.</span><span class="sxs-lookup"><span data-stu-id="d0027-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0027-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d0027-114">See Also</span></span>

- [<span data-ttu-id="d0027-115">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="d0027-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)