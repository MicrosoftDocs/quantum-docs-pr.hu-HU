---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: a539d85a4800c2f4452a1c6fe2c4f88a6296c3e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221997"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="34dec-102">RippleCarryAdderNoCarryTTK művelet</span><span class="sxs-lookup"><span data-stu-id="34dec-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="34dec-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="34dec-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="34dec-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34dec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34dec-105">Visszafordítható, helyi hullámos – a végrehajtás nélkül két egész számot is végezhet.</span><span class="sxs-lookup"><span data-stu-id="34dec-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="34dec-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="34dec-106">Description</span></span>

<span data-ttu-id="34dec-107">A LittleEndian-regisztrációban szereplő két $n $ bites egész szám, `xs` `ys` a művelet pedig kiszámítja a két egész számból álló, 2 ^ n $ adatmaradékot, ahol a $n $ a bemenetek és a méretének mérete `xs` `ys` .</span><span class="sxs-lookup"><span data-stu-id="34dec-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="34dec-108">Nem számítja ki az elvégzési bitet.</span><span class="sxs-lookup"><span data-stu-id="34dec-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="34dec-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="34dec-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="34dec-110">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="34dec-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="34dec-111">LittleEndian qubit regisztrálja az első egész szám summand kódolását.</span><span class="sxs-lookup"><span data-stu-id="34dec-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="34dec-112">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="34dec-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="34dec-113">A LittleEndian qubit regisztrálja a második egész szám summand, amely úgy módosul, hogy az összeg minimálisan jelentős bitet $n.</span><span class="sxs-lookup"><span data-stu-id="34dec-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="34dec-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34dec-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="34dec-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="34dec-115">Remarks</span></span>

<span data-ttu-id="34dec-116">A művelet ugyanazokkal a funkciókkal rendelkezik, mint a RippleCarryAdderTTK, de nem tér vissza a carry bit-nek.</span><span class="sxs-lookup"><span data-stu-id="34dec-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="34dec-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="34dec-117">References</span></span>

- <span data-ttu-id="34dec-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="34dec-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530