---
uid: Microsoft.Quantum.Preparation.PrepareQuantumROMState
title: PrepareQuantumROMState művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQuantumROMState
qsharp.summary: ''
ms.openlocfilehash: 10ad24d0772dfa254072368cf42b882ab5158bb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855865"
---
# <a name="preparequantumromstate-operation"></a><span data-ttu-id="0a1a4-102">PrepareQuantumROMState művelet</span><span class="sxs-lookup"><span data-stu-id="0a1a4-102">PrepareQuantumROMState operation</span></span>

<span data-ttu-id="0a1a4-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="0a1a4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation PrepareQuantumROMState (nBitsPrecision : Int, nCoeffs : Int, nBitsIndices : Int, keepCoeff : Int[], altIndex : Int[], data : Bool[][], indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, dataQubits : Qubit[], garbageRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0a1a4-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0a1a4-105">Input</span></span>

### <a name="nbitsprecision--int"></a><span data-ttu-id="0a1a4-106">nBitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-106">nBitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ncoeffs--int"></a><span data-ttu-id="0a1a4-107">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-107">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nbitsindices--int"></a><span data-ttu-id="0a1a4-108">nBitsIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-108">nBitsIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="keepcoeff--int"></a><span data-ttu-id="0a1a4-109">keepCoeff: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0a1a4-109">keepCoeff : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="altindex--int"></a><span data-ttu-id="0a1a4-110">altIndex: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0a1a4-110">altIndex : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="data--bool"></a><span data-ttu-id="0a1a4-111">adatkezelés: [bool](xref:microsoft.quantum.lang-ref.bool)[] []</span><span class="sxs-lookup"><span data-stu-id="0a1a4-111">data : [Bool](xref:microsoft.quantum.lang-ref.bool)[][]</span></span>




### <a name="indexregister--littleendian"></a><span data-ttu-id="0a1a4-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="dataqubits--qubit"></a><span data-ttu-id="0a1a4-113">dataQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0a1a4-113">dataQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="garbageregister--qubit"></a><span data-ttu-id="0a1a4-114">garbageRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0a1a4-114">garbageRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="0a1a4-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a1a4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

