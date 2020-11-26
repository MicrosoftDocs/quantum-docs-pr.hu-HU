---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ccef1bbf400e01800053777d0010acb7addaef53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192485"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="d19d4-102">QuantumWalkByQubitization függvény</span><span class="sxs-lookup"><span data-stu-id="d19d4-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="d19d4-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d19d4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d19d4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d19d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d19d4-105">A blokk kódolású tükröződést egy Quantum walkre konvertálja.</span><span class="sxs-lookup"><span data-stu-id="d19d4-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="d19d4-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d19d4-106">Description</span></span>

<span data-ttu-id="d19d4-107">Egy olyan `BlockEncodingReflection` egységes $U $ által képviselt, amely egyes operátorok $H $ kamatot kódol, egy Quantum walk $W $ értéket tartalmaz, amely a $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ spektrumát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="d19d4-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="d19d4-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d19d4-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="d19d4-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="d19d4-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="d19d4-110">Egy `BlockEncodingReflection` egységes $U $ értéket kell átalakítani a Quantum Walking szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="d19d4-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="d19d4-111">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d19d4-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d19d4-112">Egy Quantum Walk $W $, amely a regisztereken közösen működik `a` `s` , és blokkolja a kódolást $H $, és tartalmazza a $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ spektrumát.</span><span class="sxs-lookup"><span data-stu-id="d19d4-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="d19d4-113">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="d19d4-113">References</span></span>

- <span data-ttu-id="d19d4-114">Hamilton szimuláció a Qubitization Guang felfüggeszti Hao Low, Isaac L. a https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="d19d4-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="d19d4-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d19d4-115">See Also</span></span>

- [<span data-ttu-id="d19d4-116">Microsoft. Quantum. szimulációs. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="d19d4-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="d19d4-117">Microsoft. Quantum. szimulációs. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="d19d4-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)