---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: cc70cc409cb472a747899838d3a9ad2d78f6b5ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827697"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="a1cc4-102">ApplyBitFlipEncoder művelet</span><span class="sxs-lookup"><span data-stu-id="a1cc4-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="a1cc4-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a1cc4-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a1cc4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1cc4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1cc4-105">A bit flip Encoder és a dekóder megvalósításához használt magánhálózati művelet.</span><span class="sxs-lookup"><span data-stu-id="a1cc4-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="a1cc4-106">Vegye figyelembe, hogy ez a kódoló a helyi konzisztens helyreállítást is képes használni, ebben az esetben a kezdeti állapotában leírt hibát fogja okozni `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="a1cc4-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="a1cc4-107">Különösen, ha `auxQubits` kezdetben a $ \ket $ állapotban vannak {10} , ez $X _1 $ hibát okoz a kódolt qubit.</span><span class="sxs-lookup"><span data-stu-id="a1cc4-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a1cc4-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a1cc4-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="a1cc4-109">coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a1cc4-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="a1cc4-110">adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a1cc4-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="a1cc4-111">Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a1cc4-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="a1cc4-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1cc4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="a1cc4-113">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="a1cc4-113">References</span></span>

- <span data-ttu-id="a1cc4-114">Doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="a1cc4-114">doi:10.1103/PhysRevA.85.044302</span></span>