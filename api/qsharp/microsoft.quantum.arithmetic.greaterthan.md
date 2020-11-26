---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 644d68affbdb508938f76de5025a1a463e7284e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223085"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="e8b36-102">GreaterThan művelet</span><span class="sxs-lookup"><span data-stu-id="e8b36-102">GreaterThan operation</span></span>

<span data-ttu-id="e8b36-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e8b36-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e8b36-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8b36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8b36-105">Több mint összehasonlítást alkalmaz a qubit-regiszterbe kódolt két egész szám között, az összehasonlítás eredményétől függően a célként megadott qubit.</span><span class="sxs-lookup"><span data-stu-id="e8b36-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e8b36-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e8b36-106">Description</span></span>

<span data-ttu-id="e8b36-107">Szigorúan nagyobb, mint két egész szám összehasonlítása $x $ és $y $, a qubit-ben kódolva, az XS és az időpontot.</span><span class="sxs-lookup"><span data-stu-id="e8b36-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="e8b36-108">Ha $x > y $, akkor az eredmény qubit lesz tükrözve, ellenkező esetben az eredmény qubit meg fogja őrizni az állapotát.</span><span class="sxs-lookup"><span data-stu-id="e8b36-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="e8b36-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e8b36-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e8b36-110">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e8b36-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e8b36-111">A LittleEndian qubit regisztrálja az első egész számot $x $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="e8b36-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e8b36-112">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="e8b36-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e8b36-113">A LittleEndian qubit regisztrálja a második egész számot $y $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="e8b36-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="e8b36-114">eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8b36-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8b36-115">Egyetlen qubit, amely akkor lesz felfordítva, ha $x > y $ értéket.</span><span class="sxs-lookup"><span data-stu-id="e8b36-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8b36-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8b36-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e8b36-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e8b36-117">Remarks</span></span>

<span data-ttu-id="e8b36-118">A (z) $x-y = (x ' + y) ' $ értéket használja, ahol a "az egymást kiegészítő értéket jelöli.</span><span class="sxs-lookup"><span data-stu-id="e8b36-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="e8b36-119">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="e8b36-119">References</span></span>

- <span data-ttu-id="e8b36-120">Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="e8b36-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="e8b36-121">Thomas Haener, Martin Roetteler, Garai Viktória M. Svore: "faktoring by 2n + 2 qubits a Toffoli-alapú moduláris szorzás", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="e8b36-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>