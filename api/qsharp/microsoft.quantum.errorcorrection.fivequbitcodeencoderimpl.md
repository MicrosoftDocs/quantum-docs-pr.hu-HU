---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: f70d2d1352c7b2eebee7a863eba97d78d7351dab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200849"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="63c4e-102">FiveQubitCodeEncoderImpl művelet</span><span class="sxs-lookup"><span data-stu-id="63c4e-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="63c4e-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="63c4e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="63c4e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63c4e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63c4e-105">Az 5 qubit kódoló és a dekóder megvalósításához használt magánhálózati művelet.</span><span class="sxs-lookup"><span data-stu-id="63c4e-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="63c4e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="63c4e-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="63c4e-107">adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="63c4e-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="63c4e-108">egy 1 qubit tartalmazó tömb, amely a bemeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="63c4e-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="63c4e-109">Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="63c4e-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="63c4e-110">egy 4 qubits rendelkező tömb, amely redundancia hozzáadását.</span><span class="sxs-lookup"><span data-stu-id="63c4e-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63c4e-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63c4e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="63c4e-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="63c4e-112">Remarks</span></span>

<span data-ttu-id="63c4e-113">A kiválasztott kódoló az V. Kliuchnikov és A D. Maslov, a Clifford-áramkörök optimalizálása, a Leltárnapló. Rev. Leltárnapló. a 88, 052307 (2013). https://arxiv.org/abs/1305.08104b. ábra), és összesen 11 kaput igényel.</span><span class="sxs-lookup"><span data-stu-id="63c4e-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>