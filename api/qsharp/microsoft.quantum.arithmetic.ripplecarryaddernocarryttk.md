---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 59451b4f5c992f900a27139332059af7427b9b93
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719584"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="4e638-102">RippleCarryAdderNoCarryTTK művelet</span><span class="sxs-lookup"><span data-stu-id="4e638-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="4e638-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4e638-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4e638-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e638-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e638-105">Visszafordítható, helyi hullámos – a végrehajtás nélkül két egész számot is végezhet.</span><span class="sxs-lookup"><span data-stu-id="4e638-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="4e638-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4e638-106">Description</span></span>

<span data-ttu-id="4e638-107">A LittleEndian-regisztrációban szereplő két $n $ bites egész szám, `xs` `ys` a művelet pedig kiszámítja a két egész számból álló, 2 ^ n $ adatmaradékot, ahol a $n $ a bemenetek és a méretének mérete `xs` `ys` .</span><span class="sxs-lookup"><span data-stu-id="4e638-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="4e638-108">Nem számítja ki az elvégzési bitet.</span><span class="sxs-lookup"><span data-stu-id="4e638-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="4e638-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4e638-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4e638-110">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4e638-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4e638-111">LittleEndian qubit regisztrálja az első egész szám summand kódolását.</span><span class="sxs-lookup"><span data-stu-id="4e638-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="4e638-112">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="4e638-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4e638-113">A LittleEndian qubit regisztrálja a második egész szám summand, amely úgy módosul, hogy az összeg minimálisan jelentős bitet $n.</span><span class="sxs-lookup"><span data-stu-id="4e638-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e638-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e638-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4e638-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4e638-115">Remarks</span></span>

<span data-ttu-id="4e638-116">A művelet ugyanazokkal a funkciókkal rendelkezik, mint a RippleCarryAdderTTK, de nem tér vissza a carry bit-nek.</span><span class="sxs-lookup"><span data-stu-id="4e638-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="4e638-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="4e638-117">References</span></span>

- <span data-ttu-id="4e638-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="4e638-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530