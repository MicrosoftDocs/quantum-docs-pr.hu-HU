---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: c4466feebb8ff6afcdcb5bf385ec10e807c00537
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719585"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="e848e-102">RippleCarryAdderD művelet</span><span class="sxs-lookup"><span data-stu-id="e848e-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="e848e-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e848e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e848e-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e848e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e848e-105">Visszafordítható, helyi hullámos – két egész szám hozzáadását hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="e848e-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="e848e-106">A LittleEndian-regiszterekben és a qubit-ben kódolva két $n $ bites egész szám lett megadva `xs` `ys` , a művelet kiszámítja a két egész szám összegét, ahol az eredmény $n $ legkevésbé jelentős bitek vannak tárolva, `ys` a végrehajtás bit pedig xored a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="e848e-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e848e-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e848e-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e848e-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e848e-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e848e-109">LittleEndian qubit regisztrálja az első egész szám summand kódolását.</span><span class="sxs-lookup"><span data-stu-id="e848e-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e848e-110">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="e848e-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e848e-111">A LittleEndian qubit regisztrálja a második egész szám summand, amely úgy módosul, hogy az összeg minimálisan jelentős bitet $n.</span><span class="sxs-lookup"><span data-stu-id="e848e-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="e848e-112">Carry: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e848e-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e848e-113">A carry qubit az összeg legjelentősebb xored.</span><span class="sxs-lookup"><span data-stu-id="e848e-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e848e-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e848e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e848e-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e848e-115">Remarks</span></span>

<span data-ttu-id="e848e-116">A megadott vezérelt művelet a szimmetria és a műveletek kölcsönös megszüntetését teszi lehetővé az alapértelmezett implementációban, amely minden művelethez vezérlőelemet ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="e848e-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="e848e-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="e848e-117">References</span></span>

- <span data-ttu-id="e848e-118">Thomas G. drapéria: "kvantum-számítógép hozzáadása", 2000.</span><span class="sxs-lookup"><span data-stu-id="e848e-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033