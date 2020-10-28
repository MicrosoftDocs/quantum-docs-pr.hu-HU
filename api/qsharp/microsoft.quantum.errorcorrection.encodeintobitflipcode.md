---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712408"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="64987-102">EncodeIntoBitFlipCode művelet</span><span class="sxs-lookup"><span data-stu-id="64987-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="64987-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="64987-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="64987-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64987-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64987-105">Kódolja a [3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-flip kódot.</span><span class="sxs-lookup"><span data-stu-id="64987-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="64987-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="64987-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="64987-107">physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="64987-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="64987-108">A védeni kívánt adatmennyiséget jelképező fizikai qubits.</span><span class="sxs-lookup"><span data-stu-id="64987-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="64987-109">auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="64987-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="64987-110">A rendszer először a $ \ket $ állapotú kiegészítő qubits regisztrálja, amely a {00} védeni kívánt adatkódolásban használatos.</span><span class="sxs-lookup"><span data-stu-id="64987-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="64987-111">Kimenet: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="64987-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="64987-112">A kódoláshoz használt fizikai és kiegészítő qubits logikai regiszterként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="64987-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="64987-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="64987-113">See Also</span></span>

- [<span data-ttu-id="64987-114">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="64987-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)