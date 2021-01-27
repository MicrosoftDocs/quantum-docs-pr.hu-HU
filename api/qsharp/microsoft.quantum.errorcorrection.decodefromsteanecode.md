---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827393"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="66be5-102">DecodeFromSteaneCode művelet</span><span class="sxs-lookup"><span data-stu-id="66be5-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="66be5-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="66be5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="66be5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66be5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66be5-105">Inverz kódolási művelet, amely egy nem kódolt kvantum-regisztrációt képez le egy kódolt kvantum-regiszterbe a ⟦ 7, 1, 3 ⟧ Steane kvantum-kódjában.</span><span class="sxs-lookup"><span data-stu-id="66be5-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="66be5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="66be5-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="66be5-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="66be5-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="66be5-108">A kódolt 5 qubit kód logikai állapotát jelképező qubits tömbje.</span><span class="sxs-lookup"><span data-stu-id="66be5-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="66be5-109">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="66be5-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="66be5-110">Az 1. hosszúságú qubit tömb, amely az első paraméterben szereplő, nem kódolt állapotot jelöli, a második paraméter kiegészítő qubits együtt.</span><span class="sxs-lookup"><span data-stu-id="66be5-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="66be5-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="66be5-111">Remarks</span></span>

<span data-ttu-id="66be5-112">A kiválasztott dekóder a ⟦ 7, 1, 3 ⟧ Steane kód CSS Code tulajdonságát használja, azaz az X hibákat és a Z hibákat külön-külön kijavította.</span><span class="sxs-lookup"><span data-stu-id="66be5-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="66be5-113">A kód egy tulajdonsága az, hogy az alkalmazni kívánt X, vagy Z érték az X, a z szindróma 3 bites kódolása, ha egész számnak számít.</span><span class="sxs-lookup"><span data-stu-id="66be5-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="66be5-114">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="66be5-114">References</span></span>

- <span data-ttu-id="66be5-115">D.</span><span class="sxs-lookup"><span data-stu-id="66be5-115">D.</span></span> <span data-ttu-id="66be5-116">Gottesman, "stabilizátor-kódok és kvantum-hibák javítása" Ph.D. tézis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="66be5-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="66be5-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="66be5-117">See Also</span></span>

- [<span data-ttu-id="66be5-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="66be5-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="66be5-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="66be5-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="66be5-120">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="66be5-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)