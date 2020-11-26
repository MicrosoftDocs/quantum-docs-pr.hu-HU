---
uid: Microsoft.Quantum.Preparation.PrepareQuantumROMState
title: PrepareQuantumROMState művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQuantumROMState
qsharp.summary: ''
ms.openlocfilehash: 41b3a041ad3cef466e780fa9e88ab8ab72269e66
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193505"
---
# <a name="preparequantumromstate-operation"></a><span data-ttu-id="937c1-102">PrepareQuantumROMState művelet</span><span class="sxs-lookup"><span data-stu-id="937c1-102">PrepareQuantumROMState operation</span></span>

<span data-ttu-id="937c1-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="937c1-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="937c1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="937c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation PrepareQuantumROMState (nBitsPrecision : Int, nCoeffs : Int, nBitsIndices : Int, keepCoeff : Int[], altIndex : Int[], data : Bool[][], indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, dataQubits : Qubit[], garbageRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="937c1-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="937c1-105">Input</span></span>

### <a name="nbitsprecision--int"></a><span data-ttu-id="937c1-106">nBitsPrecision: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="937c1-106">nBitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ncoeffs--int"></a><span data-ttu-id="937c1-107">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="937c1-107">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nbitsindices--int"></a><span data-ttu-id="937c1-108">nBitsIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="937c1-108">nBitsIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="keepcoeff--int"></a><span data-ttu-id="937c1-109">keepCoeff: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="937c1-109">keepCoeff : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="altindex--int"></a><span data-ttu-id="937c1-110">altIndex: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="937c1-110">altIndex : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="data--bool"></a><span data-ttu-id="937c1-111">adatkezelés: [bool](xref:microsoft.quantum.lang-ref.bool)[] []</span><span class="sxs-lookup"><span data-stu-id="937c1-111">data : [Bool](xref:microsoft.quantum.lang-ref.bool)[][]</span></span>




### <a name="indexregister--littleendian"></a><span data-ttu-id="937c1-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="937c1-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="dataqubits--qubit"></a><span data-ttu-id="937c1-113">dataQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="937c1-113">dataQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="garbageregister--qubit"></a><span data-ttu-id="937c1-114">garbageRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="937c1-114">garbageRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="937c1-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="937c1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

