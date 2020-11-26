---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Carry művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223595"
---
# <a name="carry-operation"></a><span data-ttu-id="76448-102">Carry művelet</span><span class="sxs-lookup"><span data-stu-id="76448-102">Carry operation</span></span>

<span data-ttu-id="76448-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="76448-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="76448-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76448-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76448-105">Végrehajt egy reverzibilis Carry-kaput.</span><span class="sxs-lookup"><span data-stu-id="76448-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="76448-106">A qubit-ben és a-ben két summand-ben kódolt, a és a alkalmazásban elvégezhető átviteli sebesség miatt a `carryIn` `summand1` `summand2` kiszámítja a bitenkénti és a `carryIn` `summand1` qubit, `summand2` `summand2` valamint a végrehajtást a xored qubit `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="76448-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="76448-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="76448-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="76448-108">carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76448-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76448-109">Carry-in qubit.</span><span class="sxs-lookup"><span data-stu-id="76448-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="76448-110">summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76448-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76448-111">Első summand qubit.</span><span class="sxs-lookup"><span data-stu-id="76448-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="76448-112">summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76448-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76448-113">A második summand qubit a és a összegének alsó kis részébe kerül `summand1` `summand2` .</span><span class="sxs-lookup"><span data-stu-id="76448-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="76448-114">carryOut: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76448-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76448-115">A végrehajtás qubit az összeg magasabb xored lesz.</span><span class="sxs-lookup"><span data-stu-id="76448-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76448-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76448-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

