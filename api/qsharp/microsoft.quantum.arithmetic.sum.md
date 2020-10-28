---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Sum művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719501"
---
# <a name="sum-operation"></a><span data-ttu-id="fcdbc-102">Sum művelet</span><span class="sxs-lookup"><span data-stu-id="fcdbc-102">Sum operation</span></span>

<span data-ttu-id="fcdbc-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fcdbc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fcdbc-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fcdbc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fcdbc-105">Egy reverzibilis összegű kaput implementál.</span><span class="sxs-lookup"><span data-stu-id="fcdbc-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="fcdbc-106">A qubit-ben és a-ben két summand-ben kódolt, a és a rendszerbe bejelentkezett, a ( `carryIn` `summand1` bitenkénti) és a `summand2` `carryIn` `summand1` `summand2` qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="fcdbc-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fcdbc-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fcdbc-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="fcdbc-108">carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fcdbc-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fcdbc-109">Carry-in qubit.</span><span class="sxs-lookup"><span data-stu-id="fcdbc-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="fcdbc-110">summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fcdbc-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fcdbc-111">Első summand qubit.</span><span class="sxs-lookup"><span data-stu-id="fcdbc-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="fcdbc-112">summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fcdbc-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fcdbc-113">A második summand qubit a és a összegének alsó kis részébe kerül `summand1` `summand2` .</span><span class="sxs-lookup"><span data-stu-id="fcdbc-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcdbc-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcdbc-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fcdbc-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fcdbc-115">Remarks</span></span>

<span data-ttu-id="fcdbc-116">A `Carry` művelettel ellentétben ez nem számítja ki a végrehajtáshoz szükséges biteket.</span><span class="sxs-lookup"><span data-stu-id="fcdbc-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>