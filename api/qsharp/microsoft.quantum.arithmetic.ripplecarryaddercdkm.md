---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: 6dcb5193c5d1d059682a79e63e6562aabff7539d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719609"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="d3206-102">RippleCarryAdderCDKM művelet</span><span class="sxs-lookup"><span data-stu-id="d3206-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="d3206-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d3206-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d3206-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3206-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3206-105">Visszafordítható, helyi hullámos – két egész szám hozzáadását hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="d3206-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d3206-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d3206-106">Description</span></span>

<span data-ttu-id="d3206-107">A LittleEndian-regiszterekben és a qubit-ben kódolva két $n $ bites egész szám lett megadva `xs` `ys` , a művelet kiszámítja a két egész szám összegét, ahol az eredmény $n $ legkevésbé jelentős bitek vannak tárolva, `ys` a végrehajtás bit pedig xored a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="d3206-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="d3206-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d3206-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d3206-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d3206-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d3206-110">LittleEndian qubit regisztrálja az első egész szám summand kódolását.</span><span class="sxs-lookup"><span data-stu-id="d3206-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d3206-111">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="d3206-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d3206-112">A LittleEndian qubit-regisztrációja a második egész szám summand kódolásával módosul, hogy az összeg legalább n jelentős bitet tároljon.</span><span class="sxs-lookup"><span data-stu-id="d3206-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="d3206-113">Carry: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d3206-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d3206-114">A carry qubit az összeg legjelentősebb xored.</span><span class="sxs-lookup"><span data-stu-id="d3206-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3206-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3206-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3206-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d3206-116">Remarks</span></span>

<span data-ttu-id="d3206-117">Ez a művelet ugyanazokkal a funkciókkal rendelkezik, mint a RippleCarryAdderD, de $n $ helyett csak egy kiegészítő qubit használ.</span><span class="sxs-lookup"><span data-stu-id="d3206-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="d3206-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="d3206-118">References</span></span>

- <span data-ttu-id="d3206-119">Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.</span><span class="sxs-lookup"><span data-stu-id="d3206-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1