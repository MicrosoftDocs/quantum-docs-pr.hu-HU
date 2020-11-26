---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 19a692a3b54a413f25a474c361e773ab6c65579e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223544"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="acecc-102">CarryOutCoreCDKM művelet</span><span class="sxs-lookup"><span data-stu-id="acecc-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="acecc-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="acecc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="acecc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acecc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acecc-105">A RippleCarryAdderCDKM a fenti ApplyOuterCDKMAdder művelettel használt alapművelete, azaz a művelettel konjugált a RippleCarryAdderCDKM belső működésének beszerzéséhez.</span><span class="sxs-lookup"><span data-stu-id="acecc-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="acecc-106">Ez a művelet kiszámítja a végrehajtás qubit, és a bemenet egy részén a nem kapuk sorozatot alkalmazza `ys` .</span><span class="sxs-lookup"><span data-stu-id="acecc-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="acecc-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="acecc-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="acecc-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="acecc-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="acecc-109">Első qubit-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="acecc-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="acecc-110">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="acecc-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="acecc-111">Második qubit-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="acecc-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="acecc-112">Ancilla: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="acecc-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="acecc-113">A RippleCarryAdderCDKM a műveletnek átadott Ancilla-qubit használja.</span><span class="sxs-lookup"><span data-stu-id="acecc-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="acecc-114">Carry: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="acecc-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="acecc-115">Végezze el a qubit a RippleCarryAdderCDKM műveletben.</span><span class="sxs-lookup"><span data-stu-id="acecc-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="acecc-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="acecc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="acecc-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="acecc-117">References</span></span>

- <span data-ttu-id="acecc-118">Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="acecc-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1