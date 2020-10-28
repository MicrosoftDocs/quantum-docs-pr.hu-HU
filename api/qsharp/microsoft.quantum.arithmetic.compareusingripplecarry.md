---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721276"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="b9e39-102">CompareUsingRippleCarry művelet</span><span class="sxs-lookup"><span data-stu-id="b9e39-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="b9e39-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b9e39-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b9e39-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9e39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9e39-105">Ez a művelet azt ellenőrzi, hogy a qubits regisztere által képviselt egész szám nagyobb-e, mint egy másik egész szám, amely az eredmény XOR értékét egy kimeneti qubit alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="b9e39-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b9e39-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b9e39-106">Description</span></span>

<span data-ttu-id="b9e39-107">Két egész szám `x` és `y` azonos méretű qubit-regiszterekben tárolva a művelet ellenőrzi, hogy megfelelnek-e a követelményeknek `x > y` .</span><span class="sxs-lookup"><span data-stu-id="b9e39-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="b9e39-108">Ha az értéke TRUE (igaz), a rendszer XORed egy kimeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="b9e39-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="b9e39-109">Ellenkező esetben a 0 értéket XORed egy kimeneti qubit.</span><span class="sxs-lookup"><span data-stu-id="b9e39-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="b9e39-110">Más szóval ezt a műveletet az egységes $ $ \begin{align} U\ket {x} \ ket {y} \ ket {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)} jelképezheti.</span><span class="sxs-lookup"><span data-stu-id="b9e39-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="b9e39-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b9e39-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="b9e39-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b9e39-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="b9e39-113">x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b9e39-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b9e39-114">A qubit-regisztráció során a rendszer a következő formában tárolja az összehasonlítási számot: `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="b9e39-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="b9e39-115">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b9e39-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b9e39-116">A qubit-regisztráció során a következő formátumban tárolt értékkel összehasonlítandó második szám `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="b9e39-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="b9e39-117">kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b9e39-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b9e39-118">Az összehasonlítási $x>y $ értékének eredményét tároló Qubit.</span><span class="sxs-lookup"><span data-stu-id="b9e39-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b9e39-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b9e39-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="b9e39-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="b9e39-120">References</span></span>

- <span data-ttu-id="b9e39-121">Új kvantum-hullám – a carry addition Circuit Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="b9e39-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>