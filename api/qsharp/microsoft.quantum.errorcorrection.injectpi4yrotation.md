---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712324"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="78211-102">InjectPi4YRotation művelet</span><span class="sxs-lookup"><span data-stu-id="78211-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="78211-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="78211-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="78211-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78211-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78211-105">Egyetlen qubit elforgatása a π/4 értékkel az Y tengelyen.</span><span class="sxs-lookup"><span data-stu-id="78211-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="78211-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="78211-106">Description</span></span>

<span data-ttu-id="78211-107">Egy π/4 rotációs műveletet hajt végre `Y` .</span><span class="sxs-lookup"><span data-stu-id="78211-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="78211-108">Az elforgatás a mágikus állapot elfogyasztásával történik. Ez a másolat az állam $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="78211-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="78211-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="78211-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="78211-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="78211-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="78211-111">adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78211-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78211-112">A $ \pi/$4 értékkel el$Y forgatható qubit.</span><span class="sxs-lookup"><span data-stu-id="78211-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="78211-113">Magic: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78211-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78211-114">Egy qubit kezdetben a mágikus állapotban van.</span><span class="sxs-lookup"><span data-stu-id="78211-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="78211-115">A művelet végrehajtása után `magic` a rendszer visszaadja a $ \ket {0} $ állapotot.</span><span class="sxs-lookup"><span data-stu-id="78211-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78211-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78211-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="78211-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="78211-117">Remarks</span></span>

<span data-ttu-id="78211-118">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="78211-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="78211-119">és</span><span class="sxs-lookup"><span data-stu-id="78211-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="78211-120">Ez a művelet támogatja a (z `Adjoint` )-t, amely esetében ugyanaz a mágikus állapot használatos, de az adatqubit gyakorolt hatás a $-\ PI/4 $ $Y $-forgás.</span><span class="sxs-lookup"><span data-stu-id="78211-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>