---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725573"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="afc7f-102">QuantumWalkByQubitization függvény</span><span class="sxs-lookup"><span data-stu-id="afc7f-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="afc7f-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="afc7f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="afc7f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afc7f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afc7f-105">A blokk kódolású tükröződést egy Quantum walkre konvertálja.</span><span class="sxs-lookup"><span data-stu-id="afc7f-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="afc7f-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="afc7f-106">Description</span></span>

<span data-ttu-id="afc7f-107">Egy olyan `BlockEncodingReflection` egységes $U $ által képviselt, amely egyes operátorok $H $ kamatot kódol, egy Quantum walk $W $ értéket tartalmaz, amely a $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ spektrumát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="afc7f-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="afc7f-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="afc7f-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="afc7f-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="afc7f-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="afc7f-110">Egy `BlockEncodingReflection` egységes $U $ értéket kell átalakítani a Quantum Walking szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="afc7f-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="afc7f-111">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="afc7f-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="afc7f-112">Egy Quantum Walk $W $, amely a regisztereken közösen működik `a` `s` , és blokkolja a kódolást $H $, és tartalmazza a $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ spektrumát.</span><span class="sxs-lookup"><span data-stu-id="afc7f-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="afc7f-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="afc7f-113">References</span></span>

- <span data-ttu-id="afc7f-114">Hamilton szimuláció a Qubitization Guang felfüggeszti Hao Low, Isaac L. a https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="afc7f-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="afc7f-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="afc7f-115">See Also</span></span>

- [<span data-ttu-id="afc7f-116">Microsoft. Quantum. szimulációs. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="afc7f-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="afc7f-117">Microsoft. Quantum. szimulációs. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="afc7f-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)