---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218801"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="57ba1-102">ApplyFermionicSWAP művelet</span><span class="sxs-lookup"><span data-stu-id="57ba1-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="57ba1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57ba1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57ba1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57ba1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57ba1-105">A Fermionic-csere alkalmazása.</span><span class="sxs-lookup"><span data-stu-id="57ba1-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="57ba1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="57ba1-106">Description</span></span>

<span data-ttu-id="57ba1-107">Ez lényegében felcseréli a qubits, miközben a-1 globális fázist alkalmazza, ha mindkettő qubits: 1s.</span><span class="sxs-lookup"><span data-stu-id="57ba1-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="57ba1-108">Megőrzi a symmetrization.</span><span class="sxs-lookup"><span data-stu-id="57ba1-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="57ba1-109">További információ: .</span><span class="sxs-lookup"><span data-stu-id="57ba1-109">See  for more information.</span></span>

<span data-ttu-id="57ba1-110">Ezt a műveletet az egységes operátor \begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -1 \\ \\ \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="57ba1-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="57ba1-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="57ba1-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="57ba1-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="57ba1-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="57ba1-113">qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="57ba1-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="57ba1-114">Az első felcserélni kívánt qubit.</span><span class="sxs-lookup"><span data-stu-id="57ba1-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="57ba1-115">qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="57ba1-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="57ba1-116">A második qubit kell felcserélni.</span><span class="sxs-lookup"><span data-stu-id="57ba1-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57ba1-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57ba1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="57ba1-118">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="57ba1-118">References</span></span>

- [<span data-ttu-id="57ba1-119">*Ryan Babbush, Nathan Wiebe, Fahamvas McClean, James McClain, Hartmut neven, gránát Kin-Lic Chan*, arXiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="57ba1-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="57ba1-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="57ba1-120">See Also</span></span>

- [<span data-ttu-id="57ba1-121">Microsoft. Quantum. belső. SWAP</span><span class="sxs-lookup"><span data-stu-id="57ba1-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)