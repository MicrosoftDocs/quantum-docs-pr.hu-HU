---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: RippleCarryAdderTTK művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: cf7f8ed10de2243627a001b770a4d29ff7345f30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842951"
---
# <a name="ripplecarryadderttk-operation"></a><span data-ttu-id="aad27-102">RippleCarryAdderTTK művelet</span><span class="sxs-lookup"><span data-stu-id="aad27-102">RippleCarryAdderTTK operation</span></span>

<span data-ttu-id="aad27-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="aad27-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="aad27-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aad27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aad27-105">Visszafordítható, helyi hullámos – két egész szám hozzáadását hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="aad27-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="aad27-106">A LittleEndian-regiszterekben és a qubit-ben kódolva két $n $ bites egész szám lett megadva `xs` `ys` , a művelet kiszámítja a két egész szám összegét, ahol az eredmény $n $ legkevésbé jelentős bitek vannak tárolva, `ys` a végrehajtás bit pedig xored a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="aad27-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="aad27-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="aad27-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="aad27-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aad27-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aad27-109">LittleEndian qubit regisztrálja az első egész szám summand kódolását.</span><span class="sxs-lookup"><span data-stu-id="aad27-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="aad27-110">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="aad27-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aad27-111">A LittleEndian qubit regisztrálja a második egész szám summand, amely úgy módosul, hogy az összeg minimálisan jelentős bitet $n.</span><span class="sxs-lookup"><span data-stu-id="aad27-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="aad27-112">Carry: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aad27-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aad27-113">A carry qubit az összeg legjelentősebb xored.</span><span class="sxs-lookup"><span data-stu-id="aad27-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aad27-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aad27-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="aad27-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="aad27-115">Remarks</span></span>

<span data-ttu-id="aad27-116">A művelet ugyanazokkal a funkciókkal rendelkezik, mint a RippleCarryAdderD és a RippleCarryAdderCDKM, de nem használ Ancilla-qubits.</span><span class="sxs-lookup"><span data-stu-id="aad27-116">This operation has the same functionality as RippleCarryAdderD and, RippleCarryAdderCDKM but does not use any ancilla qubits.</span></span>

## <a name="references"></a><span data-ttu-id="aad27-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="aad27-117">References</span></span>

- <span data-ttu-id="aad27-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="aad27-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530