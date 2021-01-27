---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Sum művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847756"
---
# <a name="sum-operation"></a><span data-ttu-id="fe0cb-102">Sum művelet</span><span class="sxs-lookup"><span data-stu-id="fe0cb-102">Sum operation</span></span>

<span data-ttu-id="fe0cb-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fe0cb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe0cb-105">Egy reverzibilis összegű kaput implementál.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="fe0cb-106">A qubit-ben és a-ben két summand-ben kódolt, a és a rendszerbe bejelentkezett, a ( `carryIn` `summand1` bitenkénti) és a `summand2` `carryIn` `summand1` `summand2` qubit `summand2` .</span><span class="sxs-lookup"><span data-stu-id="fe0cb-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fe0cb-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fe0cb-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="fe0cb-108">carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe0cb-109">Carry-in qubit.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="fe0cb-110">summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe0cb-111">Első summand qubit.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="fe0cb-112">summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe0cb-113">A második summand qubit a és a összegének alsó kis részébe kerül `summand1` `summand2` .</span><span class="sxs-lookup"><span data-stu-id="fe0cb-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe0cb-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe0cb-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe0cb-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fe0cb-115">Remarks</span></span>

<span data-ttu-id="fe0cb-116">A `Carry` művelettel ellentétben ez nem számítja ki a végrehajtáshoz szükséges biteket.</span><span class="sxs-lookup"><span data-stu-id="fe0cb-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>